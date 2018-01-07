## 2.2 Měření multimetrem {#2-2-m-en-multimetrem}

![052-1.jpeg](images/00087.jpeg)

CC-BY-SA, autor André Karwath

K multimetru se dodávají dvě sondy, nejčastěji červená a černá. Černou zasuňte do zdířky, která bývá označena COM, popřípadě symbolem pro uzemnění (na obrázku úplně dole). Červenou zapojte do zdířky, která mívá označení VΩmA (na obrázku prostřední). Třetí zdířka je určená pro měření velkých napětí a proudů a je označená např. 10ADC, 10A MAX a podobně. Tu nebudete používat.

Multimetr má většinou uprostřed jeden otočný volič, kterým přepínáte měřenou veličinu (napětí, proud, odpor) a rozsah. U odporů (bývá značen velkým písmenem omega) to bývá 200, 2K, 20K, 200K a 2M. Začneme tím nejmenším, to je 200\. Přepněte volič do pozice 200, a na displeji by se měla ukázat jednička úplně vlevo – to znamená „větší odpor, než je rozsah“.

Teď zkuste na chviličku spojit oba hroty sond. Uvidíte, že číslo na displeji rychle klesne až skoro k nule. Právě jsme vytvořili zkrat – a ten má skoro nulový odpor (vlastně jen odpor samotných vodičů, a ten je minimální). Některé multimetry v takové chvíli taky pískají, to abyste věděli i bez sledování displeje, že jsou oba hroty vodivě spojeny.

Pro pořádek: symbolem „V“ a vodorovnou čárou volíte měření napětí ve voltech, případně milivoltech

![053-1.jpeg](images/00089.jpeg)

Symbolem V s vlnovkou vybíráte rozsah měření pro střídavé napětí

![053-2.jpeg](images/00093.jpeg)

Symbol A s vodorovnou čárkou znamená měření stejnosměrného proudu (v mikro - a miliampérech).

![054-1.jpeg](images/00097.jpeg)

Symbol „omega“ (Ω) označuje rozsah pro měření odporů v ohmech a kiloohmech:

![054-2.jpeg](images/00099.jpeg)

Jestli nevíte, jaký je přesně rozdíl mezi napětím a proudem, tak to teď nevadí, včas se to dozvíte. Teď jen přepněte multimetr na „200 Ω“.

Pojďme měřit. Jeden vývod rezistoru připojte na černý hrot, druhý vývod na červený, a sledujte displej. Pravděpodobně tam bude stále „1“ – tedy „odpor je větší než rozsah“. Přepněte tedy rozsah na větší – 2K. Pokud se na displeji objeví třeba „330“, tak to znamená, že měříte rezistor s odporem 330 ohmů. To není ten, co teď potřebujete (budete ho potřebovat až za chvilku). Přepněte na 20K – a pokud máte správný, tak se na displeji objeví hodnota okolo 10 – bývá to třeba 9,7, nebo 10,2 – to je stále v toleranci.

_Pro zajímavost: Zkuste si teď rezistor otočit, prohodit červený a modrý hrot, a změřte si odpor tentokrát. Jaký je? Je stejný. Rezistor je součástka symetrická, a pokud jej otočíme, tak se nic nestane._

Zpátky k blikači. Zapojte rezistor 10K mezi vývody 1 a 2 integrovaného obvodu (IO). Na obrázku je rezistor nakreslený vlevo od IO a je připojen pomocí dvou vodičů. Je to proto, že vývody 1 a 2 jsou hned vedle sebe, a rezistor se mezi ně nevejde. Další možnost je zapojit rezistor našikmo, jedním vývodem do otvoru „d“, druhým do otvoru „a“, no a poslední možnost je zapojit jej „nastojato“ – jeden vývod zkrátíte, na druhém utvoříte ohyb o 180 stupňů, a tím se oba vývody dostanou vedle sebe a můžete je zapojit do sousedních otvorů.

![055-1.jpeg](images/00100.jpeg)

_Jsme v polovině! Jupí..._

Teď zapojte kondenzátor 10 μF mezi vývody 1 a 4\. Na kondenzátory multimetr většinou nemá měřicí rozsah, ale naštěstí jsou kondenzátory větší a vejde se na ně popis. Ten váš hledaný bude vypadat jako černý nebo modrý váleček s dvěma vývody na jednom konci. U jednoho vývodu je po celé délce pouzdra bílý proužek se stylizovaným znakem „minus“. Ten vývod bývá také kratší (ale nespoléhejte na to, třeba ho někdo ucvaknul – spolehlivý je ten proužek na pouzdru). Elektrolytický kondenzátor totiž má „kladný“ a „záporný“ vývod. Zapojte jej kladným na vývod 1 integrovaného obvodu, záporným na vývod 4.

![055-2.jpeg](images/00104.jpeg)

Kdybyste teď připojili napájecí napětí, tak na vývodu 6 získáte pravidelné pulsy. Jenže je neuvidíte, neuslyšíte, neucítíte… Takže vám nezbývá, než mi to věřit – nebo si to ověřit!