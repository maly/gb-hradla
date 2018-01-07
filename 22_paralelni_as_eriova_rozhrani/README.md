# 22 Paralelní a sériová rozhraní {#22-paraleln-a-s-riov-rozhran}

Začnu zase jazykovou vsuvkou. Za socialismu se politika promítala do všeho, a i naprosto nenápadné věci byly vlastně politické. Například v technice se soudruhům nelíbilo velké množství anglických výrazů v názvosloví, a snažili se je nahrazovat českými. Tak vzniklo třeba sousloví „stykové rozhraní“. Kdybyste tápali, co to je – je to „interface“. Anglické slovo je složené ze dvou výrazů, „inter“, tedy mezi, a „face“, tedy obličej. S trochou obrazotvornosti vidíte přenos informací, který se odehrává mezi dvěma obličeji. Stykové rozhraní zní spíš jako něco ze sexuologie, ale je to totéž. Některé výrazy byly ještě mnohem horší, třeba takový magnetoskop – složenina podle vzoru „magnetofon“, která měla nahradit prohnilý západní termín „video“ – a po právy vymřely. Ze stykového rozhraní nám zůstalo alespoň to rozhraní, i když se běžně používá i počeštělá verze anglického výrazu interfejs. Jazyk si s tím poradí, přidá koncovky, zavede flexi, a tak můžeme běžně číst o interfejsech a pracovat s interfejsem.

Ale to jen na okraj.

Od počátku číslicové techniky se ukázala potřeba nějak přenášet vícebitová data. Představme si osmibitový mikroprocesor – musí nějak komunikovat s pamětí a dalšími obvody. Nejjednodušší je přenášet osmibitová data po osmici vodičů. A přesně to se dělalo.

![271-1.jpeg](images/00341.jpeg)

Datové vodiče se jmenovaly D0 až D7, a všechno, co mělo nějak přebírat data z procesoru, se posílalo po těchto osmi vodičích.

Dohromady se jim říkalo (a říká stále ještě) datová sběrnice. Proč sběrnice? Protože se k těmto vodičům připojovalo více zařízení (paměť RAM, paměť ROM, vstupně-výstupní obvody atd.) najednou, a ty samotné vodiče jako by _sbíraly_ data z různých zařízení. Samozřejmě – aby se obvody nepraly o to, kdo bude na datové vodiče posílat informace (vzpomeňte si, co jsme si říkali o připojování výstupů logických obvodů k sobě), tak jsou všechny vybavené třístavovým výstupem, tedy takovým, který umožňuje odpojení vývodu, a procesor si vždy řekne, které zařízení má komunikovat.

![272-1.png](images/000386.png)

Abychom se z toho ve schématech nezbláznili, jak taháme osm drátů kolem dokola, tak namalujeme jednu tlustou čáru, řekneme, že pro nás představuje třeba osm vodičů D0-D7, a pak jen malujeme součástky a říkáme, jak se mají napojit:

![273-1.png](images/000348.png)

Protože po takovéhle sběrnici jde těch osm bitů vedle sebe osmi vodiči, tak říkáme, že se jedná o paralelní přenos dat.

Má své výhody – třeba že přenášíme osm bitů najednou. Má ale i své nevýhody: musíme opravdu fyzicky natáhnout osm spojů, což je někdy protivná činnost a snadno se na nějaký zapomene. Druhá, větší nevýhoda je, že takto můžeme přenášet data jen na krátké vzdálenosti. Pomocí obyčejných vodičů tak na desítky centimetrů, pomocí speciálních kabelů třeba i na metr a půl, ale na delší vzdálenosti se přenos rapidně horší – dochází k chybám, k rušení, k velkému útlumu, navíc všechny nectnosti rostou s tím, jak roste rychlost přenášených dat (tedy frekvence změn). Pak už ani pořádně stíněné kabely nepomohou.

Co v takovém případě? Pak je lepší sáhnout po sériovém přenosu dat. K němu vám stačí jen pár vodičů – dva, tři, čtyři, podle typu přenosu. Se sériovým přenosem sice přenášíte data pomaleji než paralelně (máte typicky jen jeden datový vodič místo osmi), ale lépe se stíní, je odolnější proti rušení, můžete jej proto vést na delší vzdálenost…

Typickým příkladem bylo připojování tiskáren – kdysi se používalo paralelní rozhraní, známé jako Centronics. V počítačích PC bylo skryté pod označením LPT – starší počítače, ještě tak z roku 2005, ho mají na základní desce, později se už nepoužívalo. Kabely k paralelnímu rozhraní byly tlusté, krátké a drahé.

Některé tiskárny proto používaly sériové rozhraní RS-232 což je známý COM port. Takové rozhraní si v principu vystačí se třemi vodiči: data do zařízení, data ze zařízení a uzemnění. Kabel pro sériové rozhraní mohl mít třeba pět metrů, dražší a kvalitnější i víc.

Sériové rozhraní se používá dodneška pro připojení většiny periferních zařízení k počítači. Nemýlíte se, známé USB znamená _Universal Serial Bus_, a je to přesně stejný princip přenosu dat, jen vylepšený tak, aby bylo možno připojit víc zařízení naráz a používat delší kabely.

Sériový přenos se používá i v průmyslu – možná jste se setkali s rozhraním RS-485\. Dokonce i přenos videosignálu po kabelu HDMI, kterým máte pravděpodobně připojený monitor k počítači nebo třeba herní konzoli k televizi, probíhá, jak jinak, sériově.

I počítačové sítě dnes většinou fungují na principu sériového přenosu dat –Ethernet, tedy „ten kabel na sítě“, přenáší data po dvou dvojicích vodičů (další dvě dvojice jsou nepoužité).

Aby se zlepšila odolnost proti rušení indukcí, používá se u sériových rozhraní, která přenášejí data na větší vzdálenost, takzvaný „diferenciální přenos“ – jeden signál není přenášen jedním vodičem, ale kroucenou dvojicí vodičů, z nichž jeden přenáší signál, druhý jeho negaci. Přijímač pak oba vodiče porovná, a z nich dekóduje zpět přenášený signál. Vychází se z předpokladu, že případné rušení zasáhne oba vodiče stejně – oběma buď přidá, nebo ubere – ale rozdíl zůstane stejný.

Paralelní rozhraní se používá tam, kde je potřeba obrovská rychlost a stačí krátké vzdálenosti – typicky mezi procesorem a pamětí. Dříve se používalo i pro připojení dalších komponent, jako grafické karty nebo disků. Dnes se postupně přešlo i u disků a karet na sériové rozhraní (u disků SATA – Serial ATA, u karet PCI-Express, což je taky sériové rozhraní). Důvodem je zvyšování přenosové rychlosti – u sériové sběrnice je možné dosáhnout řádově vyšších rychlostí a frekvencí bez přeslechů a problémů s časováním, což trochu kompenzuje fakt, že přenášíme míň bitů najednou.

| Vlastnost | Paralelní | Sériové |
| --- | --- | --- |
| Počet najednou přenášených bitů | více (typicky 8, 16) | Většinou jen jeden |
| Přenosová rychlost | Nižší | Vyšší |
| Vzdálenost, na jakou je možno přenášet data | Menší | Větší |
| Odolnost k rušení | Malá | Větší |

V elektronické praxi se potkáte nejčastěji se sériovými sběrnicemi SPI, I2C, RS-232 (někdy označované jako UART nebo jen Serial) a 1-Wire. Paralelní rozhraní mají z často používaných komponent snad jen některé displeje. Většina ostatní techniky – senzory, aktuátory, paměti, paměťové karty atd. – používají sériová rozhraní. Důvody jsou nejen ty výše zmíněné, ale třeba i to, že řídicí obvody – jednočipy, mikrokontroléry – mohou snadno pomocí dvou či tří vývodů připojit hned několik zařízení. Pro paralelní rozhraní by bylo potřeba vývodů osm, či spíš devět (osm datových plus jeden, který říká „teď něco udělej!“)

Tak, a teď vážně: Kde bychom tak mohli použít posuvný registr? Něco mě napadá…