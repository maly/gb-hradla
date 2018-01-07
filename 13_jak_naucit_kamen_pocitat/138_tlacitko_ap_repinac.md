## 13.8 Tlačítko a přepínač {#13-8-tla-tko-a-p-ep-na}

Tlačítka, přepínače, vypínače, spínače a jiné zapínače a odpínače patří hned vedle zásuvek a žárovek k základním elektrotechnickým komponentám, které zná úplně každý z každodenní zkušenosti. Všechny tyto součástky slouží k tomu, aby buď přerušily nebo naopak spojily obvod, a to dočasně, po dobu stisknutí tlačítka, nebo trvaleji, do dalšího přecvaknutí přepínače…

Hodně o jejich funkci napoví schematické značky:

![143-1.png](images/000381.png)

Toto je schematická značka tlačítka. Všimněte si, že vodič je přerušený, a je nad ním ploška. Přesně tak vypadá tlačítko uvnitř: jsou tam dva póly a nad nimi pružný plíšek, na který tlačí plastový hmatník. Jakmile zatlačíte prstem, tak se plíšek při určitém tlaku prohne (s typickým cvaknutím) a oba póly propojí. Když tlak přestane, plíšek se opět prohne na druhou stranu a obvod zase rozpojí.

![144-1.png](images/000385.png)

Tlačítka, která budete používat nejčastěji, jsou malá mikrotlačítka, která mají čtyři vývody. Vždy dva a dva jsou spojeny dohromady, a mezi těmito dvěma páry je právě samotný mechanismus tlačítka.

Pokud si nejste jistí, které dva vývody jsou spolu propojené a které ne, tak je nejjednodušší způsob si to prostě změřit. Vážně, doporučuju…

Tlačítko tedy spíná pouze po tu dobu, kdy ho někdo tiskne, nespisovně mačká. Znáte třeba z domovního zvonku. Druhá možnost je, že tlačítko za normálních okolností vede, při stisku se naopak rozpojí, ale taková tlačítka jsou méně častá. První typ se označuje NO (Normally Open), druhý typ NC (Normally Closed), podle toho, jestli je tlačítko samo o sobě, tj. bez vnější síly, otevřené a rozpojené (NO), nebo zavřené, propojené (NC).

Pro naše experimenty s LEDkami je tlačítko dostatečně dobré zařízení, ale jakmile začnete stavět něco s rychlými procesory, zjistíte, že s tlačítkem může být problém. Totiž – člověk jednou zmáčkne, a procesor zachytí třeba dva nebo tři po sobě jdoucí stisknutí.

Tomuto efektu se říká zákmit, a je způsoben právě tím, jak je mechanicky tlačítko uspořádané. Plíšek má totiž nějakou svou pružnost, a když se „přecvakne“ do pozice _stisknuto_, tak si ještě několikrát zavibruje, a tím způsobí několik rozpojení a spojení. U pomalých obvodů to nevadí, ale rychlý jednočip napočítá klidně i několik stisknutí, a to může přinášet problémy.

Zákmity tlačítek lze řešit několika způsoby. Mechanicky – tedy použitím bezzákmitových tlačítek. Ale ta jsou velmi drahá. Pak elektricky – přidáním kondenzátoru, který rychlé pulsy odfiltruje, a Schmittova obvodu (k tomu se ještě dostaneme), který upraví signál. Nebo pomocí monostabilního klopného obvodu. No a nakonec softwarově – nejjednodušší řešení je při každém stisknutí tlačítka počkat třeba tři milisekundy (to je empiricky zjištěná hodnota pro běžná mikrotlačítka), zkontrolovat, zda je tlačítko stále stisknuté, a teprve poté dělat nějakou akci. Anglicky se těmto postupům říká debouncing – občas se s tím setkáte, tak abyste věděli…

Přepínač funguje podobně, ale „pamatuje si“ poslední stav.

Uvnitř bývá mechanická propojka, která vždy spojí prostřední vývod (společný, C – Common) s jedním z krajních vývodů. Mechanismus je navržen tak, aby k přepnutí došlo co nejrychleji, skokově, aby se minimalizovala doba, kdy jsou oba vývody odpojené a aby se vyloučilo, že budou zapojené oba naráz. (Existují i přepínače se třemi polohami, kdy uprostřed jsou oba vývody odpojené.)

Přepínač nemusí být jen páčkový, jak jej známe ze starších elektronických výrobků. Může být třeba posuvný.

![145-1.png](images/000393.png)![145-2.jpeg](images/00403.jpeg)

Tento přepínač se dá, při troše dobré vůle, použít i do nepájivého kontaktního pole. Bohužel, rozteč vývodů u některých laciných přepínačů může být pouze 2,5 mm, ne 2,54, a tak lehce nesedí, což je škoda. Snažte se proto sehnat takové, které mají rozteč 2,54 mm.

Pokud u přepínače jeden krajní vývod vynecháme, dostaneme spínač (popřípadě vypínač, ono je to totéž). Velmi časté jsou spínače a přepínače dvoupólové, tedy takové, kde jsou vlastně dva spínače / přepínače v jednom pouzdru, jen páčka je společná. Abychom se v tom trochu vyznali, tak jsou zavedené zkratky:

SPST – Single pole (jednopólový), single throw (s jedním vývodem, tedy spínač)

SPDT – Single pole (jednopólový), dual throw (s dvěma vývody, tedy přepínač)

DPST – Dual pole (dvoupólový), single throw (s jedním vývodem, tedy spínač)

DPDT – Dual pole (dvoupólový), dual throw (s dvěma vývody, tedy přepínač)

![146-1.jpeg](images/00412.jpeg)