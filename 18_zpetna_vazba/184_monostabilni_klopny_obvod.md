## 18.4 Monostabilní klopný obvod {#18-4-monostabiln-klopn-obvod}

Pojďme si zase něco vymyslet… Třeba… Pamatujete se na to zapojení s tlačítkem, kondenzátorem a LEDkou, jak se tlačítkem nabil kondenzátor a pak se pomalu vybíjel přes rezistor a svítila nám LEDka? Dalo by se to nějak zapojit s integrovaným obvodem?

Co třeba takhle… Bude tam kondenzátor a rezistor. Kondenzátor se nabije, nějak, to teď nebudeme řešit. No a pak se bude pomalu vybíjet přes ten rezistor, a až se vybije pod určitou mez, tak to nějak přepne výstup.

![213-1.png](images/000239.png)

Tak, a teď dvě otázky: jak zajistit ten výstup, a jak zajistit to úvodní nabití?

Výstup bude jednodušší: prostě na tu horní část připojíme invertor, ideálně se Schmittovým vstupem. Takto:

![213-2.png](images/000282.png)

Na výstupu bude tedy v klidu logická 1, když bude kondenzátor nabitý, bude na výstupu 0, a jak bude napětí klesat, tak v určitém bodě se invertor opět přepne do 1.

To bychom měli. Teď jak zajistit to nabití? Co třeba stejně, tedy přivést do téhož místa výstup z invertoru. Ten dodá dostatečný proud pro nabití kondenzátoru. Je důležité, aby ten startovací puls měl nějakou minimální délku, aby se kondenzátor stihl nabít. Čím větší kondenzátor, tím delší čas pro nabití.

Zkusíme to tedy takhle:

![214-1.png](images/000335.png)

Otázka za sto bodů: proč jsem použil na vstupu invertor se Schmittovým obvodem, když by tam mohl být klidně obyčejný? Nemá to žádnou komplikovanou příčinu, prostě jen vím, že invertory se dělají v pouzdrech po šesti, a když použiju obvod 7414, mám v něm šestici invertorů se Schmittovým obvodem na vstupu. Tak ho rovnou použiju, když je v témže pouzdru. Proč bych tam dával další pouzdro, že?

Zkusíme to, ale nebude to fungovat. Fakt, klidně si to zkuste, ať vidíte sami, že to nic nedělá. Proč?

Na vstupu by měla být 1, na výstupu 0\. To je klidový stav. Pak na vstup přivedete 0\. Na výstupu bude 1, kondenzátor se nabije… oukej… na vstup zase vrátíme 1, na výstupu bude tedy nula, a… Aha! Už jsem to říkal, ale zopakujme si: Když je na výstupu 0, znamená to, že uvnitř obvodu je výstup spojen se zemí. Takže jakmile se výstup levého invertoru přepne do 0, tak se kondenzátor bleskurychle vybije právě přes ten výstup.

Chtělo by to nějakou součástku. Nějakou takovou, která by pustila proud jen z výstupu ven, ale už ne zpátky dovnitř. Nějakou, co pouští proud jen jedním směrem…

A zatímco přemýšlíte, jaká součástka by to mohla být, tak já si tu něco jen tak nakreslím:

![215-1.png](images/000067.png)

Bude to fungovat? No, zkuste si.

[eknh.cz/mono](https://eknh.cz/mono)

Celé téhle báječné věci se říká „monostabilní klopný obvod“. Jako že má jeden stabilní stav (1), vnější puls jej na chvíli přepne do druhého stavu (0), a obvod se po čase vrátí zpátky do stabilního. Proto mono-stabilní.

Délku trvání výstupního pulsu nastavíte kombinací kapacity C1 a odporu R1\. Délka pulsu je přibližně 0,8.R.C (dosaďte ohmy, farady a výsledek vyjde v sekundách). Přesněji řečeno: doba, o kterou je opožděno přepnutí obvodu proti konci pulsu na vstupu. Dejme tomu: kondenzátor 10 µF, rezistor 100 kΩ, čas by tedy měl být zhruba 0,8 sekundy. Jakmile přivedete na vstup 0, výstup se taky přepne do nuly. Dokud bude na vstupu nula, na výstupu bude taky nula. Od okamžiku, kdy se vstup vrátí do 1, to bude trvat 0,8 sekundy, než se do stavu 1 vrátí i výstup.

Pokud někdy během té 0,8 sekundy přijde další impuls, začne se počítat až od jeho konce. Když tedy budete posílat na vstup pulsy třeba každých 0,5 sekundy, obvod se bude znovu a znovu spouštět, a výstup bude stále 0\. Takovým monostabilním klopným obvodům se říká _znovuspustitelné_ (retriggerable) – vstupní puls jakoby znovu spustil odpočet. Existují i takové MKO, které v aktivním stavu ignorují vstupní signály, a je možné je znovu aktivovat až poté, co se přepnou zpět do klidového stavu (nonretriggerable).

Zkuste si, pro zajímavost, vymyslet, jak zařídit, aby se náš monostabilní klopný obvod stal _non-retriggerable_, tedy aby vždy zareagoval na puls pouze v klidovém stavu. Není to tak těžké, stačí si uvědomit, že potřebujeme vlastně jen to, aby ve stavu 0 (aktivní) neprošly na vstup žádné pulsy… Svoje řešení si můžete porovnat s tím mým:

[eknh.cz/monotrig](https://eknh.cz/monotrig)

A co kdybychom chtěli, aby byl klidový stav klopného obvodu v 0, a aktivní v 1? Šlo by to? Šlo, jen je třeba zajistit opačné fungování, tedy že impuls na vstupu (1, po inverzi 0) nabije kondenzátor. Jak může „nula“ nabít kondenzátor? No tak, že jej zapojíme proti napájecímu napětí. I vybíjení tak bude probíhat přes rezistor na napájecí napětí…

[eknh.cz/monopos](https://eknh.cz/monopos)

![216-1.png](images/000014.png)