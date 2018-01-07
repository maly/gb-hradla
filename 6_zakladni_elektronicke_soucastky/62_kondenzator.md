## 6.2 Kondenzátor {#6-2-kondenz-tor}

Kondenzátor je součástka, která umí uchovat elektrický náboj. Pokud připojíme kondenzátor k baterii, nabije se a náboj si udrží i po odpojení. Když pak připojíme k vývodům spotřebič, náboj do něj může přejít. Množství náboje, které kondenzátor dokáže pojmout, určuje jeho charakteristika, zvaná kapacita. Jednotkou kapacity je farad, v praxi se ale používají jednotky v řádech miliontin (mikrofarad) až biliontin (pikofarad). Dlouho platilo, že reálně dostupné kapacity jsou tisíce mikrofaradů (milifarady), ale v posledních letech s rozvojem nových materiálů začaly být dostupné i superkondenzátory s kapacitou v řádech stovek faradů, které dokáží napájet obvody po dlouhou dobu, vyrovnávat proudové odběry atd.

Kondenzátor v té nejjednodušší podobě tvoří dvě destičky, které jsou velmi blízko sebe, ale mezi nimi je izolant. V minulosti byly hojně používané např. svitkové kondenzátory, což byly vlastně dvě pásky z tenké hliníkové fólie, proložené izolační fólií a stočené do ruličky.

![110-1.jpeg](images/00287.jpeg)

Dnes se nejčastěji v číslicové technice setkáme s kondenzátory keramickými a elektrolytickými. Keramické kondenzátory se hodí pro menší kapacity v řádech nano- a pikofaradů. Pro větší kapacity v mikrofaradech se používají kondenzátory elektrolytické, v nichž je v roli izolantu speciální roztok – elektrolyt. Tyto kondenzátory mají několik nectností. V první řadě jsou citlivé na přepólování, proto mají označený kladný a záporný vývod a je potřeba dodržet orientaci. Druhá nectnost těchto kondenzátorů je, že časem degradují, vysychají a ztrácejí svoje vlastnosti. Pokud jde o levnější kusy, mohou přestat fungovat už po několika letech. Elektrolytické kondenzátory bývají nejčastější příčinou toho, že i relativně nová elektronika přestane fungovat. Používají se hlavně v napájecích obvodech, a to proto, že dokážou udržet velký náboj a pokrýt okamžiky zvýšeného odběru. Jakmile ale takový kondenzátor zestárne, ztratí schopnost udržet náboj a zařízení pak funguje s chybami, vypíná se nebo nefunguje vůbec. Leckdy stačí pouze tyto kondenzátory vyměnit a vše bude zase fungovat.

Když kondenzátor zapojíme sériově do obvodu, například s LED, kde prochází stejnosměrný proud, zjistíme, že proud prochází jen velmi krátkou dobu po zapnutí, pak přestane. Kondenzátor stejnosměrný proud nevede – ostatně je uvnitř izolant. Ovšem vlivem elektrické indukce vyvolá změna napětí (změna!) na jednom vývodu změnu náboje na vývodu druhém. Při rychlých změnách napětí na jednom pólu může tímto způsobem proud skrz kondenzátor procházet. Čím větší kapacita, tím pomalejší změny (tedy _nižší frekvence_) skrz kondenzátor projdou.

Proto se kondenzátor používá jako filtr. Tam, kde potřebujete například odfiltrovat příliš rychlé změny ze signálu (protože víte, že to je třeba rušení), připojíte paralelně kondenzátor. Rychlé změny projdou skrz něj (do zkratu).

![111-1.jpeg](images/00299.jpeg)

Minipokus: Zapojte si takovýto obvod:

![111-2_.png](images/000138.png)

[eknh.cz/cap](https://eknh.cz/cap)

Co se bude dít? Jakmile stisknete tlačítko, začne svítit dioda, a zároveň se začne nabíjet kondenzátor C1 (a část proudu poteče skrz něj, ovšem jak se bude kondenzátor nabíjet, bude tento proud klesat k nule). Když tlačítko po chvíli pustíte, přestane do LED téct proud z baterie, ale LED bude dál svítit. Bude ji pohánět náboj z kondenzátoru, který se pomalu vybíjí přes rezistor R1 do diody. Poznáme to podle toho, že dioda nezhasne hned, ale bude postupně zhasínat, zhasínat, až zhasne. To se stane ve chvíli, kdy napětí na kondenzátoru poklesne pod prahové napětí, nutné k rozsvícení a otevření diody.

![112-1.jpeg](images/00150.jpeg)

Zkuste si pokus opakovat s různými kondenzátory a různými velikostmi rezistoru. Když budete měřit, jak dlouho to trvá, než LEDka přestane svítit, zjistíte, že tato hodnota je přímo úměrná kapacitě i odporu; čím větší je odpor a čím větší je kapacita, tím pomaleji se kondenzátor vybíjí a tím déle bude svítit. Samozřejmě, jakmile bude rezistor příliš velký, bude proud LEDkou tak malý, že LED bude svítit nepozorovatelně.