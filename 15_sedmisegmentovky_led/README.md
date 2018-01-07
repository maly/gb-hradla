# 15 Sedmisegmentovky LED {#15-sedmisegmentovky-led}

Odpočiňme si na chvíli od kombinačních obvodů a podívejme se na něco mnohem atraktivnějšího. Podívejme se na známé _digitální osmičky_, ze kterých se dělaly displeje. A ačkoli vypadají jako osmičky, říká se jim _sedmisegmentovky_. Správně vlastně „sedmisegmentová zobrazovací jednotka“, ale než to řeknete, tak posluchači usnou.

Bývaly doby, kdy sedmisegmentovka představovala ultramoderní techniku. Když chtěli ve filmu tvůrci ukázat, jak doba kvačí a budoucnost je na dosah, vrzli tam něco, co zobrazovalo na displeji ze sedmisegmentovek nějaké číslice. Sedmisegmentovky jsme pak všichni měli v kapesních kalkulačkách a digitálních hodinkách.

![183-1.png](images/000264.png)

Sedmisegmentovka má opravdu sedm segmentů. Označují se tradičně písmeny A až G, od horního vodorovného po směru hodinových ručiček, prostřední vodorovný je pak poslední. Jenže naprostá většina sedmisegmentovek má vstupů osm: poslední je desetinná tečka, nebo dvojtečka. Sedmisegmentovek je spousta různých druhů, dělají se sdružené displeje po dvou číslicích, po čtyřech, po osmi, dělají se speciální „hodinové“ displeje, které mají jeden a půl pozice…

Sedmisegmentovky se skládají ze sedmi (s tečkou z osmi) svítících diod (LED), které jsou paralelně spojené. Ovšem je otázka, jak jsou spojené, jestli katodami, nebo anodami.

![184-1.png](images/000318.png)![184-2.png](images/000375.png)

Podle toho, jestli je sedmisegmentovka se společnou katodou (CC, Common Cathode), nebo se společnou anodou (CA, Common Anode), se bude lišit i práce s ní. U sedmisegmentovky se společnou katodou se společný vývod zapojuje na zem, a segmenty budou svítit tehdy, když bude na příslušný vstup přivedeno kladné napětí (tedy log. 1). U společné anody tomu bude obráceně – společná anoda je zapojena na kladné napájecí napětí, a segment, který má svítit, musí mít vstup v log. 0, neboli uzemněný.

![184-3.jpeg](images/00329.jpeg)

Samosebou nesmíme zapomenout na rezistory ke každému segmentovému vstupu. Uvnitř jsou úplně stejné LED jako známe, tak je potřeba se k nim i stejně chovat.

Poznámka: Nechme teď stranou displeje z kapalných krystalů (LCD). Samozřejmě existují i v podobě sedmisegmentovek, ale jejich princip není tak jednoduchý a vyžadují trošku specifičtější zacházení.

Pomocí sedmisegmentovky můžeme zobrazit 127 různých znaků, které ukazuje následující obrázek.

![185-1.png](images/000041.png)

Většinou se používají číslice 0 až 9 a některá písmena. Pokud chcete lepší ztvárnění písmen i číslic, můžete použít zobrazovače se 14 nebo 16 segmenty, nebo pak matici bodů.

![186-1.png](images/000354.png)

Pro displeje ze sedmisegmentovek existují speciální obvody – dekodéry, které převádějí (většinou čtyřbitovou) informaci na sedm bitů pro sedmisegmentovku. O nich jsem se už zmiňoval v kapitole o dekodérech a kombinační logice.

### 15.0.1 Mimochodem… {#15-0-1-mimochodem}

Sedmisegmentovky jsou dnes už velmi levné, ale bývaly to poměrně drahé součástky. Dnes už i ty staré, původní, seženete defacto „na váhu“, za pár korun. S některými výjimkami, jako jsou obvody TIL od Texas Instruments. Šlo o jedny z prvních sedmisegmentovek, a výrobce Texas Instruments třeba do modelu TIL 306 či TIL307 zamontoval i integrovaný obvod, který fungoval jako čítač a jako dekodér.

![186-2.jpeg](images/00155.jpeg)

Taková sedmisegmentovka je dnes skoro malý poklad, protože její ceny na aukčních serverech jsou okolo dvou set korun za jeden kus. Podobně i jejich klony z bývalého NDR, jako je například VQC10\. Ovšem pokud stavíte něco, co má mít „retro vzhled“, budou tyto displeje naprostým hitem.

![187-1.jpeg](images/00376.jpeg)

Další oblíbený displej byl takzvaný „bublinkový“. Šlo o několik sedmisegmentovek, spojených do jednoho bloku (většinou po 4, 8 nebo 9). Nad každou sedmisegmentovkou byla plastová „bublinka“, která fungovala jako čočka a zvětšovala titěrné symboly tak, aby byly čitelné. Podobné displeje se používaly převážně v kalkulačkách.

![188-1.jpeg](images/00244.jpeg)

No a když už jsme v tom retrovzpomínání, tak se dodneška můžeme potkat s takzvanými „nixie“ displeji – vypadaly jako elektronky, a nebyly zapojené po segmentech, ale měly speciálně tvarované vlákno pro každou číslici. Vyráběly se i v Sovětském svazu, kde se jim říkalo Itrony.

![188-2.jpeg](images/00390.jpeg)