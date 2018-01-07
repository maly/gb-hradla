# 2 Postavte si blikač – teď už to snad půjde lépe {#2-postavte-si-blika-te-u-to-snad-p-jde-l-pe}

Budete potřebovat:

• Integrovaný obvod 7404 (v té variantě, jakou máte, tedy i 74LS04, 74ALS04, 74HCT04)

• Elektrolytický kondenzátor 10 μF

• Rezistor 330 Ω

• Rezistor 10 kΩ

• LED libovolné barvy

• Nepájivé kontaktní pole

• Napájecí obvod

• Propojovací kabely (Poslední tři položky budete potřebovat vždy, tak už je nebudu opakovat)

Bez dalšího vysvětlování si pojďte poskládat obvod na nepájivém kontaktním poli. Výsledek bude vypadat nějak takto:

![049-1.jpeg](images/00080.jpeg)

Nejprve se podívejte na nepájivé kontaktní pole. Všimněte si, jak je toto pole uspořádané. Nahoře a dole (z tohoto pohledu) jsou dvě oddělené lišty, označené červeným a modrým proužkem. To jsou napájecí lišty, které slouží k rozvádění napájecího napětí do obvodu. Jsou uspořádané do pětic a jsou spolu uvnitř pole vodivě propojeny horizontálně, jak je naznačeno na následujícím obrázku.

Střední část pole je uspořádána jinak – zde je horní a dolní polovina, a v nich jsou vždy jednotlivé pětice otvorů propojeny svisle (a-b-c-d-e, f-g-h-i-j). Je to výhodné uspořádání pro součástky, které mají dvě řady vývodů, jako náš integrovaný obvod 7404\. Takový obvod přesně sedne doprostřed, a každý jeho vývod je připojen ke čtyřem dalším otvorům, takže máte dostatečný prostor na propojování.

![050-1.jpeg](images/00082.jpeg)

Než vytáhnete integrovaný obvod z obalu, tak se nejprve uzemněte. Sáhněte třeba na radiátor. Statická elektřina je prevít a některé citlivé obvody můžete zničit tím, že na ně sáhnete. Pokud máte 74ALS04 nebo 74LS04, tak ty tak citlivé nejsou, ale některé řady (74HCT04) a bez výjimky všechny složitější obvody jsou na statickou elektřinu velmi citlivé. Proto se většinou prodávají zapíchané v proužku vodivé pěny, která udržuje všechny vývody propojené, a tudíž se nestane, že by na jednom vývodu bylo velmi vysoké napětí oproti ostatním.

Jste uzemněni? Tak se podívejte na integrovaný obvod. Jsou na něm nejčastěji různé značky výrobce (ST, TI, F), pak čísla výrobních sérií, země původu, a někde mezi tím bude skryto i to označení 7404\. U mne to je konkrétně T74LS04B1\. „T“ označuje výrobce, 74LS04 je typ obvodu a technologie, a B1 je upřesňující označení – teplotní rozsah, pouzdro atd.

Vývody integrovaného obvodu jsou očíslované od 1, jenže na pouzdru tato čísla nikde nejsou. Proto si pamatujte základní poučky, jak zjistit orientaci:

• Když si dáte obvod tak, aby označení bylo čitelné, tak většinou (ne vždy!) bývá vývod číslo 1 vlevo dole. Ale toto pravidlo není stoprocentně spolehlivé.

• Podívejte se na pouzdro. Na jedné z kratších stran bude značka – vlys, výbrus, malý žlábek, … Když držíte pouzdro tak, aby tato značka byla vlevo, tak je vývod číslo 1 zase vlevo dole.

• Někdy výrobce i na tuto značku kašle, a místo toho označí nějak vývod 1\. Buď barevnou tečkou, nebo třeba miniaturním důlkem.

• Když všechno selže, podívejte se do datasheetu. Později si vysvětlíme, co to datasheet je.

Když víte, jak je obvod orientovaný, tak ho zasuňte do pole tak, jak je nakresleno na úvodním obrázku. Nepůjde to, vývody trochu nepasují – je to proto, že vývody jsou z výroby lehce „rozkročené“. Proto je decentním tlakem z obou stran o trochu narovnejte, aby byly rovnoběžné. Já k tomu používám plochu stolu. Stačí opravdu maličko. Pak obvod půjde bez problémů zasunout do nepájivého kontaktního pole. Zasuňte ho tak, aby vývod 1 byl vlevo dole, třeba v otvoru „10e“. Je to jedno, ale aspoň se v tom lépe vyznáte.

![051-1.png](images/000084.png)

Máte-li vývod 1 vlevo dole, tak číslování pokračuje proti směru hodinových ručiček – napravo od 1 je 2, pak 3, 4, až k vývodu číslo 7\. Naproti němu je vývod číslo 8 (vpravo nahoře), a číslování pokračuje až k vývodu 14 (vlevo nahoře). Obvod 7404 totiž používá čtrnáctivývodové pouzdro (značí se DIL14 nebo DIP14). Některé obvody mají pouzdra větší – 16 vývodů, 24 vývodů, 28, 40, někdy i víc. Ale obvykle platí, že od určitého počtu vývodů se obvody primárně dělají v pouzdrech pro povrchovou montáž (SMD – Surface Mount Device), které mívají přes sto miniaturních vývodů. Ty ale my používat nebudeme.

Máte zasunutý obvod, je to tak? Nejprve k němu připojíme napájení. Vývod 7 připojte k modré (záporné) napájecí liště, vývod 14 k červené (kladné). Proč zrovna tyto dva a takto, to se později dozvíte, teď prosím jen následujte můj popis.

Pomocí propojovacích vodičů spojte vývody 2 a 3\. Dalším vodičem spojte vývody 4 a 5.

Zapojte rezistor 10 kΩ mezi vývody 1 a 2.

Aha? A který rezistor to je, že?