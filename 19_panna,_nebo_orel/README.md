# 19 Panna, nebo orel? {#19-panna-nebo-orel}

To takhle sedíte u počítače a přemýšlíte: Mám napsat teď kapitolu o posuvných registrech, nebo raději nějakou praktickou konstrukci? Jak se rozhodnout? Co třeba hodit mincí?

Problém je, pokud jste moderní člověk s bezhotovostními penězi. To si můžete tak akorát hodit platební kartou, a to, uznejte sami, není ono. Můžete si taky pustit počítač a naprogramovat si házení mincí… Anebo si můžete postavit elektronickou házecí minci.

Jako správní nadšenci do číslicové techniky se pustíme do té poslední varianty. Racionální hlas uvnitř hlavy ironicky podotýká, že je to varianta sice nejdražší, zato zabere nejvíc času. Nadšenecký hlas ale říká: _No a co? Aspoň se u toho něco naučím!_

Zapojení bude jednoduché. Budou tam dvě LED, a bude svítit vždy jen jedna z nich. Pokaždé, když obsluha zmáčkne tlačítko, tak se jedna z nich rozsvítí. Která? No, to by mělo být náhodné!

Zařízení samozřejmě nemusíme používat nezbytně nutně jen na házení mincí. Hodí se třeba i pro chovatele Schrödingerovy kočky, kde poměrně kvalitně simuluje otvírání krabice, a pro spoustu dalších zásadních životních rozhodnutí. Sice nedokáže simulovat stav „mince padla na hranu“, „mince zapadla mezi prkna v podlaze“ a „mince zůstala viset ve vzduchu“, ale na hrubou náhradu to jistě stačí.

![232-1.jpeg](../images/00051.jpeg)

Tak. Princip máme. Jak to teď celé poskládat? Vyjdeme od konce, tedy od těch zobrazovacích LEDek. Je potřeba, aby zůstávaly v jednom ze dvou stavů. Tady by se hodilo mít třeba něco jako – jo, něco jako klopný obvod D, který má dva výstupy, Q a /Q, které jsou vždy takříkajíc „v opozici“. No a k nim připojíme ty dvě LED, jednu z nich označíme „panna“ a druhou „orel“ (ti, co si staví Schrödingerovu krabici, si LED označí „živá číča“ a „mrtvá číča“).

Zobrazování bychom měli taky. Teď co s tím tlačítkem?

Vzpomeňte si na kapitolu, kde jsme si představovali obvod 7474 – dvojici klopných obvodů typu D. Mají dva synchronní vstupy, totiž D a CLK. A vstup CLK funguje tak, že propustí do obvodu stav na vstupu D, a to ve chvíli, kdy se na tomto vstupu změní úroveň z log. 0 do log. 1, což je přesně to, co potřebujeme. Přesně tohle totiž udělá naše tlačítko, pokud ho zapojíme na + 5 V – jakmile ho obsluha stiskne, změní se stav z 0 V na + 5 V. To je ta „vzestupná hrana“, která spustí požadovanou akci.

Teď ještě tu náhodu. Jak to zařídit?
