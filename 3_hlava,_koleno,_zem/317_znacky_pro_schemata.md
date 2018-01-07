## 3.17 Značky pro schémata {#3-17-zna-ky-pro-sch-mata}

Když se podíváte na zapojení našeho blikače na nepájivém kontaktním poli, zjistíte, že není moc přehledné. Není z toho jasné, co se tam děje a proč. Proto se používají schematické značky a nákresy – schémata. _Prosím, čtěte to [schéma], ne [šéma]!_ Schéma obsahuje všechny součástky a jejich spojení tak, aby bylo člověku, který obvod staví, jasné, co má kde použít a s čím propojit. Schematické značky slouží, podobně jako třeba notový zápis nebo vývojový diagram, k tomu, aby bylo jasné, co a jak je v obvodu zapojené, i když to v reálu vypadá naprosto jinak.

Na schématu neřešíte velikosti, vzdálenosti, nic z toho. Nejdůležitější je, aby schéma bylo dobře čitelné a srozumitelné. Proto se vynechávají detaily, které nejsou podstatné – například u schématu blikače nakreslím jen někam značku „tady bude zem a tady + 5 voltů“, a neřeším, jak a kde se tam vezme. Když nakreslím zem na schématu někam vlevo a pak nakreslím zem někde vpravo, tak není potřeba explicitně udávat, že jsou ty vývody ve skutečnosti propojené, protože jsou oba vodivě připojeny do jednoho místa. To si každý konstruktér pořeší sám. Dál je dobrým zvykem postupovat stejně jako v textu, tedy kreslit schéma tak, že signál jde zleva doprava a shora dolů.

Na značky samozřejmě existují normy a výklady a vykladači, schopní se kdykoli pohádat o kanonickém tvaru té které značky, ale v praxi se setkáte třeba se schématy, které nakreslil někdo v USA a použil lehce jiné značky, než jaké známe my. Důležitější je proto srozumitelnost a pochopitelnost. Pokud je třeba jedno, jestli se zařízení napájí z baterie, nebo ze stabilizovaného zdroje, tak někam prostě jen nakreslím značku, k ní připíšu „+ 5 V“, a každému je jasné, že se do toho bodu musí nějak dostat + 5 voltů, a že tedy někde bude nějaký bod, označený jako „zem“ (silnější vodorovná čárka), a tam přijde druhý pól napájení.

Základem jsou symboly pro vodiče a jejich spojení. To je prostá čára. Pokud se dvě čáry kříží, neznamená to, že jsou spojené. Pokud mají být spojené, je v místě křížení výrazná tečka.

Projděte si nejčastější symboly, s nimiž se setkáte. Za chvíli si o součástkách, které představují, řekneme víc.

V tabulce uvádím značky tak, jak jsou v databázi programu Eagle – de facto standardu pro amatérskou tvorbu schémat a desek plošných spojů. A přidávám i anglické názvy, protože se s nimi často setkáte.

![080-1.png](images/000137.png)

Vodič (Wire)

![081-1.png](images/000339.png)

Křížení vodičů bez spojení (Wire crossing)

![081-2.png](images/000141.png)

Spojení vodičů (Junction)

![081-3.png](images/000142.png)

Monočlánek (Power cell)

![081-4.png](images/000145.png)

Baterie (Battery)

![081-5.png](images/000384.png)

Rezistor (vlevo evropský symbol, vpravo americký) (Resistor)

![081-6.png](images/000149.png)

Rezistor s proměnným odporem (potenciometr), trimr (Potentiometer, variable resistor)

![081-8.png](images/000400.png)

Kondenzátor (vlevo evropský symbol, vpravo americký) (Capacitor)

![082-1.png](images/000153.png)

Polarizovaný (elektrolytický) kondenzátor (vlevo evropský symbol, vpravo americký) (Electrolytic capacitor)

![082-2.png](images/000417.png)

Cívka (Coil)

![082-3.png](images/000158.png)

Transformátor (Transformer)

![082-4.png](images/000016.png)

Dioda (Diode)

![082-5.png](images/000162.png)

LED (Světlo vyzařující dioda)

![082-6.png](images/000032.png)

Schottkyho dioda

![082-7.png](images/000168.png)

Bipolární tranzistor NPN (Bipolar Junction Transistor – BJT, NPN type)

![083-1.png](images/000050.png)

Bipolární tranzistor PNP (Bipolar Junction Transistor – BJT, PNP type)

![083-2.png](images/000171.png)

Tranzistory v Darlingtonově zapojení (Darlington BJT)

![083-3.png](images/000077.png)

Tranzistor JFET-N (JFET N-type)

![083-4.png](images/000175.png)

Tranzistor MOSFET-N (MOSFET N-channel, N-type)

![083-5.png](images/000108.png)

Tranzistor MOSFET-P (MOSFET P-channel, P-type)

![083-6.png](images/000004.png)

Spínače a přepínače (Switch, Momentary Switch)

![084-1.png](images/000001.png)

Tlačítko (Push button)

![084-2.png](images/000024.png)

Napájení, uzemnění (Voltage, Power, Supply; Ground)

_A to jsou všechny značky?_ Ale kdepak, kdepak, ještě jich bude spousta, nebojte… Včas si je ukážeme.

### 3.17.1 Kroužek, nebo ne? {#3-17-1-krou-ek-nebo-ne}

Některé součástky (tranzistory, diody) mívají schematické značky uzavřené do kroužku. Kroužek symbolizuje pouzdro součástky. Pokud se kreslí tranzistory v integrovaném obvodu, měly by se kreslit bez kroužku. Tak hovoří norma. Jenže zase platí, že norma něco říká, ovšem v praxi narazíte na leccos. Pokud používáte program pro kreslení schémat, jste odkázáni na to, jak autoři tuto problematiku pojali, jestli připravili značky s kroužkem, nebo bez. _Máte dvě možnosti: buď se rozčilovat, že autoři neumí nakreslit značku tranzistoru s kroužkem podle normy, nebo se s tím smířit. Doporučuju druhý způsob, tedy přijmout fakt, že svět není dokonalý, a ušetřit čas, který byste strávili domalováváním kroužků do schémat, vytvořených v nějakém nástroji._

##### 4 Zdroje napětí {#4-zdroje-nap-t}