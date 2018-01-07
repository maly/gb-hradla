## 14.12 Otevřený kolektor, třetí stav, OE {#14-12-otev-en-kolektor-t-et-stav-oe}

Průběžně tu na to narážím, tak je načase vysvětlit, oč jde.

Už jsem tu říkal, že nesmíme jen tak spojit výstupy hradel TTL „nakrátko“. Nejen že by tekly obvodem úplně zbytečné proudy, ale navíc by ani nebylo jasné, jaká hodnota je na výstupu – jednotlivá hradla by se o vedení přetahovala a vyhrálo by to nejsilnější. Proto: ne, nikdy, nikdy, nikdy!

Jenže! Občas potřebujeme, aby se na jedno společné vedení připojovalo víc funkčních jednotek. Třeba na datové sběrnici procesoru je připojená paměť RAM, paměť ROM a různé periferie, a podle adresy se vybírá konkrétní obvod, s nímž se komunikuje. Až dosud dobrý, ale teď mi řekněte: Co mají dělat ostatní obvody, připojené tamtéž, se svými výstupy? Nemůžou být ani v log. 1, ani v log. 0, tím by totiž rušily přenos dat.

![169-1.png](images/000170.png)

Co mají udělat? Jedna z možností je použít obří multiplexor, a připojovat vždy pouze jediné zařízení. Jenže když si představíte, jak by to vypadalo u osmibitového počítače: máme třeba pět zařízení (RAM, ROM, časovač, paralelní port, sériový port), každé po osmi bitech, to je 40 bitů, dalších 8 bitů výstup, 3 bity řídicí – jen ten multiplexor by měl pouzdro větší než celý procesor!

V praxi se na to jde jinak. Existuje totiž něco, čemu se říká třetí stav. Označuje se Z, říká se mu taky „stav vysoké impedance“ a znamená to, že obvod má výstup odpojený. Zkrátka neposílá na něj ani logickou 0, ani logickou 1, zkrátka nic. Fyzicky se uvnitř obvodu odpojí jak od země, tak od napájecího napětí.

Ne každý obvod má třístavové výstupy. Hradla, o nichž jsme se až dosud bavili, to většinou neumožňují. Složitější součástky, třeba dnes popsané demultiplexory, nebo třeba paměti či procesory, ale mají možnost, jak své výstupy odpojit. U pamětí, dekodérů, demultiplexorů a podobných najdeme vstup, který se jmenuje OE, tedy „output enable“. Pokud je 1, obvod funguje normálně, pokud je 0, jsou všechny vývody nastavené do stavu Z, tedy odpojené.

Díky tomu může být na jedné datové sběrnici připojena paměť RAM i ROM i periferie. Všechny tyto obvody mají totiž výstupy ve stavu Z, a procesor si určí, ze kterého chce číst. Tomu pak povolí přístup na sběrnici tím, že mu pošle signál OE.

![170-1.png](images/000416.png)

U jednoduchých obvodů máte k dispozici buď budiče s třístavovým výstupem (a), popřípadě takové, kde je řídicí vstup negovaný (b), anebo invertory s třístavovým výstupem (c).

Speciálním typem třístavových zařízení, s nimiž se setkáte i u hradel, je takzvaný výstup s otevřeným kolektorem. Setkáte se s ním i dnes poměrně běžně – třeba sběrnice I2C, používaná pro připojování senzorů (v dalším textu si ji představíme), má právě tento druh výstupů. Většina lidí si vystačí s tím, že si pamatují, že „k takovému výstupu musí přidat pull-up rezistor“, ale my si teď řekneme i důvod, proč tomu tak je.

Výstup s otevřeným kolektorem má dva stavy: logickou 0, při níž je výstup spojen se zemí, a logickou 1, při níž je výstup odpojený (stav Z). Vzpomeňte si na naše zapojování tlačítka – tohle je obdobný stav. Pokud spolu spojíme vodičem výstupy s otevřeným kolektorem, máme dvě možnosti: Buď jsou všechny výstupy v logické 1, jsou tudíž odpojené a na spojovacím vodiči je v tu chvíli „nic“, nebo je některý z výstupů v logické 0, a spojovací vodič je tedy spojen se zemí.

Na takto spojené výstupy s otevřeným kolektorem se připojuje přes dostatečně velký rezistor, třeba 10k, napájecí napětí. V klidovém stavu, když jsou výstupy odpojené, je tak na výstupech přes tento rezistor napájecí napětí, a tedy logická 1\. Pokud některý z výstupů sepne k zemi, bude na vedení logická 0\. Samozřejmě si to můžeme nasimulovat pomocí přepínačů a žárovek, princip je stejný.

Řekněme, že máme tři stanoviště, kde může vzniknout poplach, a chceme, aby vždy všechna stanoviště viděla, že na některém vznikl poplach. Máme opět spoustu možností, ale když zvolíme „otevřený kolektor“, vystačíme si s jediným signálovým vodičem.

![171-1.png](images/000173.png)

Za normálního stavu, tedy v klidu, je signálový vodič připojen k žárovkám na jednotlivých stanovištích, a zároveň přes rezistor k napájecímu napětí. Je na něm tedy logická 1\. Jakmile se na některém ze stanovišť přepne přepínač k zemi, tedy k logické 0, uzavře se obvod tak, že poteče proud přes žárovky na stanovištích přes tento přepínač k zemi. Žárovky se rozsvítí, a o to nám šlo!

U velmi často používané sběrnice I2C se jedná o podobný postup (stejně jako u 1-Wire – obě sběrnice vám v pravý čas představím). Zařízení jsou datovými vodiči s otevřeným kolektorem připojeny k signálu SDA, a v klidu je tento signál „zvedán“ k log. 1 rezistorem. Pokud je třeba vyslat data, tak buď procesor, nebo zařízení (podle toho, jak se předem domluví), posílá data tak, že buď „stahuje výstup k nule“, nebo jej nechává odpojený (=log. 1).