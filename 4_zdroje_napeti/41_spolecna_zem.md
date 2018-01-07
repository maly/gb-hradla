## 4.1 Společná zem {#4-1-spole-n-zem}

Představte si, že máte dva obvody. Jeden je napájený třeba z USB, například Arduino. Druhý obvod je napájený nějak jinak, třeba vlastní baterií, nebo adaptérem ze sítě – třeba ovladač dveřního zámku. A vy teď chcete, aby se nějaký signál z Arduina dostal k tomu ovladači, protože stavíte automatický kódový zámek… Jak to uděláte?

Tak samozřejmě, nejprve zjistíte, jestli jsou obě zařízení kompatibilní, jestli Arduino dá dost proudu na to, aby zámek sepnul, ale dejme tomu, že to je ověřené, že u zámku je napsáno „Arduino compatible, 5 V logic“, takže to spojit můžete.

Tak spojíte Arduino a vstup zámku vodičem, a budete se moc divit, že to nefunguje. Proč? Odpověď je prostá:

Arduino na výstup pošle + 5 voltů, třebas. Jenže jak jsme si říkali: volty jsou vždy „mezi něčím a něčím jiným“ – u Arduina to je + 5 voltů mezi výstupem a jeho zemí (GND). Elektronický zámek to má ale úplně stejně: očekává napětí 5 voltů mezi vstupem a svojí zemí.

Proto je potřeba zajistit, aby _má zem byla i tvá zem_ (jak se říká vznešeně ve slavnostních řečech hned předtím, než vyhubí domorodce). Nejjednodušší způsob, jak to zajistit, je prostě to spojit. Spojte vodivě zem u Arduina se zemí u zámku, čímž zajistíte společnou neutrální úroveň a to, že všechno, co bude + 5 voltů nad potenciálem země u Arduina bude i + 5 voltů nad potenciálem země u elektronického zámku. A v tu chvíli se všechno jako zázrakem zprovozní a začne fungovat.

Nezapomeňte: Pokud spolu mají komunikovat dva obvody, musí mít spojené „zemní“ pól napájení. Tomuto spojení se říká společná zem, ještě na to několikrát narazíme, a je to docela důležité pravidlo, které si pamatujte!

S tím souvisí ještě jedno pravidlo, a to je to, že když spolu spojujete několik spotřebičů (například počítač a monitor), tak by měly být ve stejné zásuvce. Někdy se může stát, že dvě různé zásuvky mají různou fázi, což v důsledku vede k tomu, že jejich „země“ nejsou totožné a je mezi nimi napětí (nebudu se pouštět do podrobností, ale je to tak). Když zapojíte počítač do jedné zásuvky, monitor do druhé, je to OK – ale pak spojíte monitor s počítačem. V tu chvíli propojíte zem u obou spotřebičů. Pokud má každá zásuvka jinou fázi, a tudíž i jiný zemní potenciál, začne téct docela velký proud z jedné zásuvky skrz počítač, videokabel a monitor do druhé. A máte problém.

##### 5 Vedle sebe, za sebou {#5-vedle-sebe-za-sebou}
