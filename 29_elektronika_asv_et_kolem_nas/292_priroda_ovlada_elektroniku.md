## 29.2 Příroda ovládá elektroniku {#29-2-p-roda-ovl-d-elektroniku}

Stejně jako je někdy potřeba, aby elektronika ovládala svět okolo nás, tak bývá potřeba, aby naopak nějak reagovala ona na to, co se kolem ní děje. Třeba na to, že uživatel stisknul tlačítko nebo že vzrostla teplota.

### 29.2.1 Tlačítka a klávesy {#29-2-1-tla-tka-a-kl-vesy}

Tyto součástky jsem už popisoval, tak jen pro pořádek připomenu: Jedná se o mechanické součástky, které při stisknutí buď vodivě sepnou dva vývody, nebo je naopak rozepnou, popřípadě přepnou. Můžete uspořádat větší množství tlačítek do podoby klávesnice, buď se samostatnými tlačítky, nebo (častěji) do matice.

### 29.2.2 Dotyk {#29-2-2-dotyk}

Tlačítko potřebuje, aby člověk vyvinul nějaký tlak prstem a mechanicky tak posunul spínací element do požadované polohy. Existují ale obvody, které reagují na přiblížení či dotyk. Nejčastěji jsou postavené jako kondenzátor, a princip jejich funkce je ten, že přiblížení prstu vyvolá změnu kapacity.

![333-1.jpeg](images/00095.jpeg)

### 29.2.3 Světlo – fotorezistor, fotodioda, line tracking {#29-2-3-sv-tlo-fotorezistor-fotodioda-line-tracking}

Princip fotorezistoru jsem už probíral. Citlivější a rychlejší snímání světla umožňují polovodičové fotodiody a fototranzistory. Opět se využívá citlivosti polovodiče na světlo.

Pokud potřebujete z nějakého důvodu oddělit dva obvody od sebe, můžete využít takzvaný _optocoupler_. Česky se používá termín _optočlen_. Jde o součástku, která v jednom pouzdru integruje LED a fototranzistor. LED funguje tak, jak jste zvyklí, a intenzita jejího světla otvírá nebo zavírá fototranzistor.

![333-2.png](images/000311.png)

Optické oddělovače se používají například u dlouhých datových vedení, kde není zajištěno, že budou obvody na obou koncích připojené ke stejné úrovni země, a při prostém propojení by hrozilo zničení velkým proudem.

Dvojice LED – Fototranzistor se používá třeba i v detektorech přiblížení nebo ve světelných závorách. U snímačů přiblížení se obě součástky umístí vedle sebe. LED vysílá pravidelné pulsy, a pokud se přiblíží nějaký předmět, který dostatečně odráží světlo (třeba i prst), odrazí se puls i do fototranzistoru.

![334-1.jpeg](images/00210.jpeg)

Samozřejmě takový detektor nebude moc fungovat, pokud k němu přiblížíte černé těleso, které, jak známo, moc světla neodráží (proto je ostatně černé). Tento efekt se používá například u robotů, kteří dokážou sledovat nakreslenou čáru. Robot svítí před sebe na zem, a několik fototranzistorů snímá odražené světlo. Pokud se neodráží žádné, znamená to, že u daného fototranzistoru je pravděpodobně nakreslená černá vodicí čára.

### 29.2.4 Magnetismus {#29-2-4-magnetismus}

Pro snímání magnetického pole může sloužit cívka – ovšem ta, jak víte, indukuje napětí pouze tehdy, když se magnetické pole mění. Pro použití v číslicové technice je vhodnější Hallova sonda. Ta je tvořena polovodičovou destičkou, skrz níž prochází proud. Když tuto sondu vložíte do magnetického pole, indukuje se na ní napětí, které je možné měřit.

Složitější součástky (magnetometry, digitální kompasy) dokáží měřit i zemský magnetismus ve třech osách a dát tak informaci o tom, v jaké pozici se zařízení nachází. Nemusíte se ale bát – i takovéhle součástky jsou dostupné pro běžnou amatérskou praxi. Většinou používají rozhraní I2C. Příkladem může být obvod HMC5883L.

### 29.2.5 Otáčení, posun {#29-2-5-ot-en-posun}

Pro snímání mechanického pohybu existuje celá řada řešení, podle toho, co se má vlastně detekovat. Buď se snímá posun na nějaké dráze, nebo otáčení, popřípadě kombinace obojího.

Nejjednodušší měření otáčení a posunu představují otočné a tahové potenciometry. Jejich nevýhoda je, že mají omezený rozsah (u posunu pár centimetrů, u otáčení většinou necelou jednu otáčku, nanejvýš jen několik málo otáček). Výhoda je, že víte, v jaké pozici se nachází jezdec, jestli to je na kraji nebo třeba uprostřed.

Při snímání otáček můžete použít rotační enkodér. Vzpomeňte si: otáčet můžete donekonečna, a dvojice spínačů říká, že se osa pootočila o nějakou definovanou část, a jakým směrem. Výhoda je to, že můžete točitstále dokola, nevýhoda je, že nevíte, jak je právě nastavená osa. Víte jen, že se otáčí.

Mechanické snímání rotačním enkodérem má i další nevýhodu – časem se opotřebují kontakty. Tuto nevýhodu odstraňují jiné metody snímání otáček: optické (na hřídeli jsou světlé a tmavé části, a pomocí LED a fototranzistoru snímáte, jestli je k vám natočena světlá nebo tmavá část), nebo třeba magnetické (v hřídeli jsou magnety a snímá se magnetické pole Hallovou sondou). Pokud máte jen jeden měřicí element (jednu sondu, jeden fototranzistor), dokážete snímat rychlost, ale nezjistíte směr. Pokud použijete dva vedle sebe, zjistíte i směr (podle toho, v jakém pořadí budou aktivní). Pokud je potřeba určit i úhel natočení, použije se rozdělení na mnoho segmentů (pro zvýšení přesnosti), a k tomu jeden další prvek, který vždy oznámí, když se sledovaný objekt natočí do úhlu 0.

Pro snímání posunu lze použít stejného principu – třeba nakreslit na dráhu pravidelně se střídající černé a bílé proužky a pomocí LED a fototranzistorů odečítat pulsy.

### 29.2.6 Poloha, zrychlení {#29-2-6-poloha-zrychlen}

Z mobilních telefonů jistě víte, že tato zařízení dokážou zjistit, v jaké jsou pozici – jestli leží na stole, nebo jestli je někdo zdvihnul, jestli je držíte na výšku nebo na šířku a spoustu dalších věcí. K tomu slouží součástky, zvané akcelerometry a gyroskopy.

Akcelerometr měří zrychlení ve třech osách (X, Y, Z). Pokud je zařízení v klidu, působí na něj tíhové zrychlení Země. Akcelerometr dokáže toto zrychlení detekovat. Když zařízením otočíte, změní se hodnoty tíhového zrychlení pro jednotlivé osy.

Vlastností zrychlení je, že se skládá jako vektor, takže samotný akcelerometr nedokáže rozpoznat, jestli síla, která na něj působí, je zemská tíže, nebo zrychlení při pohybu. Případný pohyb tak může zaměnit za náklon. Tuto nectnost odstraňuje druhá součástka, gyroskop. Ta zase neměří zrychlení, pouze určuje, jestli se změnila orientace zařízení v prostoru – tedy jestli jste s ním otočili.

V moderních součástkách se často kombinuje akcelerometr, gyroskop a kompas, a taková součástka dokáže podat hodně komplexní informaci o tom, v jaké pozici se zařízení nachází. Příkladem takové součástky je MPU9150 – je sice složitá a komplexní, ale s okolím komunikuje přes sběrnici I2C. Práce s ní, například v Arduinu, je tedy velmi snadná.

### 29.2.7 Zvuk {#29-2-7-zvuk}

K detekci zvuků se používají téměř výlučně mikrofony. Nejjednodušší použití jsou „hlukoměry“, které nedetekují, o jaký zvuk jde, ale jen to, že vznikl nějaký hluk – třeba tlesknutím. Složitější obvody s vlastními procesory dokážou rozpoznávat vzorky slov a implementovat tak třeba jednoduché hlasové ovládání. Takové obvody pak komunikují se zařízením pomocí nějakého standardizovaného rozhraní (sériový port např.)

Druhá možnost zpracování zvuku je, že signál z mikrofonu vzorkujete pomocí rychlého analogově-digitálního převodníku (ADC) a zvuk tak _samplujete_. Pokud je rychlost čtení vzorků dostatečně vysoká (třeba hudební CD používají 44,1 kHz) a přesnost alespoň 12 bitů, získáte velmi slušný záznam zvuku k dalšímu zpracování.

### 29.2.8 Teplota, vlhkost {#29-2-8-teplota-vlhkost}

Termistor i obvod LM35 jsme si už představili. Představili jsme si i digitální teploměr LM75 s rozhraním I2C. Moc víc vám toho stran měření teploty neukážu – samozřejmě jsou i další součástky, které mají vyšší přesnost, ale princip zůstává stejný.

Zajímavý doplněk jsou senzory relativní vlhkosti. Jejich princip je jednoduchý – obsahují substrát, který pohlcuje vlhkost, a k němu jsou připojené dvě elektrody. Čím je substrát vlhčí, tím menší je jeho odpor, takže měřením odporu se pak lehce zjistí vlhkost. Odpor samozřejmě záleží i na teplotě, a tak bývají často vlhkoměry kombinované v jednom pouzdru i s teploměrem.

Často používané senzory jsou DHT11 a DHT22 – jsou levné a dostupné a jejich připojení k Arduinu je extrémně snadné. Jediný problém je s jejich ovládáním. Nepoužívají totiž standardní sběrnice, ale přenáší data po jednom vodiči, podobně jako sběrnice 1-Wire (ale ne úplně stejně). Naštěstí to řešit nemusíte, protože existují hotové a vyzkoušené knihovny.

### 29.2.9 Vzdálenost {#29-2-9-vzd-lenost}

Jednu z možností, jak měřit vzdálenost, jsme si už ukazovali – bylo to měření vzdálenosti pomocí ultrazvuku. Na podobném principu pracují i takzvané Time-of-Flight (ToF) senzory, ovšem místo (ultra)zvuku používají světelný paprsek. Jenže světlo letí mnohem rychleji, tak i přesnost měření musí být o hodně vyšší. Naštěstí zase existují součástky, které vše potřebné zařídí za vás.

![337-1.jpeg](images/00248.jpeg)

ToF senzor je ta černá obdélníková součástka uprostřed, ta se dvěma malými otvory.

### 29.2.10 Tlak {#29-2-10-tlak}

Takovým „hello world“ pro konstrukce s Arduinem bývá domácí meteostanice. To takhle vezmete digitální teploměr, digitální vlhkoměr a digitální tlakoměr, připojíte to k Arduinu a během deseti minut měříte všechno možné. Nejčastěji používaným tlakoměrem je BMP180 (nebo přesnější BMP085), který integruje měření tlaku a teploty. Asi vás ani nepřekvapí, že opět komunikuje přes rozhraní I2C.

Měření tlaku vyžaduje korekci podle nadmořské výšky, protože tlak vzduchu, jak známo, s rostoucí nadmořskou výškou klesá. Tlak, který naměříte, se proto přepočítává k univerzálnímu vztažnému bodu, totiž na „hladinu moře“. Anebo to můžete celé udělat naopak, a ze znalosti skutečného tlaku a naměřeného určit nadmořskou výšku.

### 29.2.11 Plyn {#29-2-11-plyn}

Zajímavé senzory jsou takové, které detekují přítomnost plynů či prachu ve vzduchu. Princip prachových snímačů je prostý – vzduch prochází komorou se stanoveným objemem. Do této komory bliká intenzivní světlo z LED a měří se, jaká část projde skrz a jaká část se rozptýlí na prachových částicích.

Senzory plynů se nejčastěji používají elektrochemické – obsahují destičku z látky, která reaguje s určitými plyny, jako je metan, propan, butan, páry etanolu, oxid uhelnatý, vodík, ozon, čpavek atd. Při reakci vzniká elektrické napětí, které se měří a podle jeho velikosti lze usuzovat na koncentraci daného plynu.

Jiný způsob měření používá technologii NDIR – Non-Dispersive Infra Red Sensors. Tyto senzory využívají toho, že určité plyny pohlcují záření určitých vlnových délek. Opět tedy používají komoru, do které svítí jasným světlem a měří úbytek světla přesně dané vlnové délky.

### 29.2.12 GPS {#29-2-12-gps}

Co bylo před dvaceti lety fantazií ze stránek populárně-naučných magazínů, to je dnes leckdy běžně dostupnou realitou. Jako příklad můžu jmenovat třeba GPS – systém geolokace pomocí družicového signálu. Vlastně extrémně složité zařízení, které přijímá signál z družic, u nichž jsou známy přesně jejich pozice, a z posunu signálu dopočítává přesnou pozici přijímače, tedy zeměpisnou délku, šířku i nadmořskou výšku.

Takové přijímače nejsou úplně nejlevnější, stojí i několik set korun, ale jsou bez problémů dostupné i pro amatérské konstrukce. Navíc mnohé z nich dokáží využít kromě amerického systému GPS i ruský Glonass a evropský Galileo.

![338-1.jpeg](images/00049.jpeg)

Připojení takových přijímačů je navíc extrémně jednoduché, protože naprostá většina z nich používá jednosměrné sériové rozhraní UART s rychlostí přenosu 4800 Bd. Přijímač posílá neustále informace o pozici a dalších hodnotách pomocí takzvaného protokolu NMEA. Jedná se o velmi jednoduchý protokol, co řádek, to informace. Přijímač posílá různé typy informací, ta, která vás asi bude zajímat nejvíc, začíná znaky „$GPRMC“ a za nimi je 11 hodnot, oddělených čárkami. Například takto:

$GPRMC, 225446, A,4916.45, N,01511.12, E, 000.5, 054.7, 090717, 020.3, E*68

• 225446 je čas měření – 22:54:46 UTC

• A informuje, jestli je měření platné – A = Valid position, V = Warning

• 4916.45,N Šířka 49 deg. 16.45 min. North (severní)

• 01511.12,E Délka 15 deg. 11.12 min. East (východní)

• 000.5 Rychlost vůči Zemi (v uzlech – knots, 1 knot = 1.852 km/h)

• 054.7 Azimut pohybu

• 090711 Datum měření (UTC)

• 020.3,E Magnetická odchylka 20.3 stupňů východně

• *68 Kontrolní součet

Kromě vět GPRMC posílá přijímač i další (GPGSA – seznam dostupných družic, GPGSV – informace o pozici viditelných družic apod.), které ale asi nebudete využívat.

### 29.2.13 Pohyb osob (PIR) {#29-2-13-pohyb-osob-pir}

Zajímavé čidlo, kterým tento přehled uzavřu, je pasivní infračervené čidlo pohybu (Passive Infra Red – PIR). Čidla PIR jsou nápadná svým zakrytováním – ve skutečnosti jde o Fresnelovu čočku, která zaostřuje infračervené záření z okolí na snímací prvek. Vlastní element je zase polovodičová součástka, která je citlivá na infračervené světlo. To vyvolává změnu napětí, ta je detekována citlivým tranzistorem typu FET a dále zpracovávána.

![339-1.jpeg](images/00351.jpeg)

PIR se používají pro detekci toho, že je nablízku člověk. Lidské tělo totiž vyzařuje, jako každý teplý objekt, infračervené záření. U lidského těla má toto záření vlnovou délku 9,4 μm. jsou tedy často používané pro detekci pohybu osob, ať už vítaného (např. u spínání osvětlení v garáži), nebo nevítaného (poplachové systémy).

Nevýhodou může být přílišná citlivost – pokud je příliš velká, zachytí čidlo i menší živočichy, například kočku či psa. Hodně záleží i na místě instalace čidla – případné proudění teplého vzduchu může čidlo zmást.

##### 30 Meteostanice {#30-meteostanice}