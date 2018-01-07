## 20.8 Počítadlo k autodráze {#20-8-po-tadlo-k-autodr-ze}

Neejn k autodráze, samozřejmě. Můžet ho použít kdekoli, kde je potřeba počítat, kolikrát se něco stane.

U autodráhy třeba průjezd autíčka. Když už se závodí, tak ať je jasné, kdo projel kolik kol. Jak na to?

No, bude potřeba zjistit, že autíčko projelo nějakým měřicím bodem. Možností je, jako vždy, několik, ale nejjednodušší bude spolehnout se na staré dobré světlo. Šel by sice použít třeba mechanický spínač, ale předpokládám, že by autíčko mohlo mít trošku problém a ve vysoké rychlosti by mohlo vyletět z dráhy. Světlo bude lepší.

Když světlem, tak jak? Buď můžete vzít LED, tu dát na jednu stranu dráhy, na druhou naproti dát fotorezistor, a pak sledovat, kdy dojde k zatmění. Pardon, k zastínění. Pro zvýšení citlivosti můžete dát na obě součástky malé plastové trubičky a nasměrovat je přesně proti sobě, aby je tolik neovlivňovalo okolní světlo.

Druhá možnost je použít takzvané reflexní snímače, známé též pod označením „detektory přiblížení“ (anglicky „optical reflective sensor“, případně „line tracking sensor“ – třeba typ TCRT5000). Technicky to je LED a fototranzistor v jednom bloku:

![265-1.jpeg](images/00323.jpeg)

Pokud nemáte autíčka úplně černá, tak fototranzistor zachytí světlo, odražené od jeho povrchu, a dokáže tak detekovat průjezd.

Zapojení takového snímače je jednoduché: LED připojte přes rezistor k napájecímu napětí. Fototranzistor zapojte podobně jako tlačítko, tedy kolektor přes pull-up rezistor cca 10 kΩ k napájecímu napětí, emitor k zemi, a výsledek odebírejte z kolektoru. Na výstup dejte, kvůli snazšímu zpracování signálu, Schmittův klopný obvod (třeba v invertoru 7414).

![266-1.png](images/000333.png)

Za normálního stavu LED svítí, ale na fototranzistor nic nedopadá. Fototranzistor je tedy zavřený, na vstup invertoru jde přes rezistor 10k napájecí napětí, tedy log. 1, a na výstupu je logická 0\. Jakmile se před senzor dostane autíčko, LED osvítí jeho povrch, odražené světlo sepne fototranzistor, tím se na vstup Schmittova obvodu dostane zem, a na výstupu bude 1.

S touto informací už můžete dál pracovat. Nejjednodušší je zase připojit Arduino s displejem, počítat pulsy a zobrazovat je na displeji.

Pojďme ale zvolit „staré dobré obvodové řešení“. Existuje totiž obvod, který v sobě kombinuje desítkový čítač, dekodér pro sedmisegmentovky a budič. Jeho označení je SN74143\. Když se podíváte do datasheetu, zjistíte, že je to přesně to, co potřebujeme.

Plni nadšení ho jdete koupit, a zjistíte, že ho pravděpodobně neseženete. V katalogu už je označen jako „Obsolete“ a už se ani nevyrábí.

Podobný obvod se ale stále vyrábí v CMOS řadě 40xx, tentokrát s označením CD4026\. V pouzdru DIP16 je desítkový čítač, dekodér a budič.

![267-1.png](images/000344.png)

Vstup 1 slouží k přivedení vstupních pulsů. Vstup 2 (clock inhibit) slouží k přerušení čítání. Připojte ho na zem (nechceme přerušovat). Vstup 3 (display enable) slouží ke zhasínání displeje. Nechceme, proto jej připojte na napájecí napětí. Výstup 4 nechte být (odpovídá hodnotě na vstupu 3), výstup 5 taky (pokud nebudete dávat dva čítače za sebe, abyste získali vícemístné počítadlo). Vývody 6, 7, 9, 10, 11, 12, 13 odpovídají jednotlivým segmentům LED sedmisegmentovky, Vss je zem a Vdd je napájení (CMOS můžete napájet až 15 volty). Vstup 15 je RESET, ten si připojte přes tlačítko na napájecí napětí, a k němu pulldown rezistor. Získáte tak možnost vynulovat počítadlo. Vývod 14 ponechte být.

Sedmisegmentovku (zvolte typ „se společnou katodou“) připojte samozřejmě přes oddělovací rezistory. Zapojte si to takto na kontaktním poli, jako vstup dejte zase tlačítko s pulldown rezistorem, a zkoušejte, jestli vše počítá jak má.

Proč se společnou katodou? Protože pak má sedmisegmentovka vyvedené anody od segmentů a katody spojené do jednoho vývodu. Jednotlivé segmenty svítí, když se na ně přivede napájení. Sedmisegmentovky se společnou anodou to mají obráceně, ty svítí, když se vývod segmentu propojí se zemí. Šly by použít, ale museli byste buď zapojit invertory, nebo tranzistory.

Když se začtete do datasheetu, zjistíte, že vstupy CLOCK a CLOCK INHIBIT mají na vstupu Schmittův klopný obvod, takže můžeme ten invertor vynechat. Hurá, o jeden obvod méně.

Problém je, že teď naše čidlo má na výstupu 1 a průjezd autíčka způsobí 0, zatímco obvod 4026 očekává naopak vzestupné pulsy. Ale lze to vyřešit velmi elegantně: v datasheetu naleznete vnitřní schéma obvodu. V něm uvidíte, že vstupy CLOCK a CLOCK INHIBIT jsou vlastně stejné, jen INHIBIT je negovaný. Uvnitř jsou pak spojené hradlem AND. Takže můžeme připojit výstup senzoru na CLOCK INHIBIT, a CLOCK zapojit na napájecí napětí. Za normálního stavu tak bude na vnitřních hodinách 0 (protože CLOCK INHIBIT=1), jakmile projede autíčko, vypne se CLOCK INHIBIT (=0), a tím se uvnitř obvodu vytvoří vzestupná hrana.

Pokud zjistíte, že jeden průjezd autíčka vyvolá vícero impulsů, můžete zkusit buď umístit senzor jinam, nebo třeba polepit autíčko stříbrnou fólií, popřípadě na výstup z čidla dát kondenzátor, který odfiltruje rychlé pulsy a sleje je do jednoho. Čítači to, díky Schmittovu obvodu, vadit nebude.

##### 21 Posuvné registry {#21-posuvn-registry}