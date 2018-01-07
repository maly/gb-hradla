## 1.2 „Dílna“ {#1-2-d-lna}

Být programátorem je velmi snadné. Stačí vám k tomu počítač a židle. Ani ten stůl není potřeba, zvládnete to totiž na koleni. Doslova. S elektronikou je to trochu těžší – minimálně ten stůl potřebujete, protože pracujete s malými součástkami a nechcete, aby vám padaly na koberec.

Neříkám, že potřebujete hned dílnu s ponkem a spoustou přístrojů, ale něco přeci jen mít musíte. V téhle knize vám budu ukazovat základy elektroniky, a budu se snažit, abyste se při tom neměli šanci ani zranit, ani zničit vybavení bytu. Bude vám stačit jen místo na stole, dostupná zásuvka, pořádné světlo a pár nástrojů a pomůcek. Něco z toho možná doma máte, pokud ne, tak to pořídíte v libovolném obchodě, ať už kamenném, nebo internetovém. Pár tipů najdete v další kapitole.

Co tedy nakoupit? V první řadě nepájivé kontaktní pole. Anglicky se tomu říká _breadboard_, a je to deska s maticí otvorů, které jsou vždy po pěti propojené. Do těchto otvorů zasunujete vývody součástek a spojujete je pomocí drátků, pokud nevyjdou vývody do správné pětice. Díky tomu nemusíte pracovat s páječkou, a zároveň je zapojený obvod snadno rozebiratelný, takže můžete zapojení sestavovat a opět rozmontovávat bez rizika, že součástky třeba nadměrnou tepelnou zátěží poškodíte.

![038-1.jpeg](images/00365.jpeg)

K nepájivému kontaktnímu poli je vhodná i sada propojovacích vodičů. V zásadě můžete použít jakýkoli izolovaný drát s tloušťkou kolem 0,3 mm, ale doporučím koupit speciální vodiče pro nepájivá kontaktní pole. Tyto vodiče mají na koncích plastové koncovky, díky kterým se snáze zastrkávají i vytahují. V ČR jsou z nějakého důvodu nehorázně drahé, ale pokud je koupíte přes internet z e-shopů v zahraničí, můžete se dostat na zlomek ceny. Hledejte _jumper wire_ nebo _dupont wire_.

![039-1.jpeg](images/00055.jpeg)

Když už budete kupovat propojovací vodiče, kupte si nejen „male-male“, tedy „samec-samec“, ale i „male-female“ a „female-female“. Tedy vodiče, které mají na jednom či obou koncích dutinky. Budou se hodit pro připojování modulů k Arduinu.

![039-2.jpeg](images/00058.jpeg)

Budete potřebovat občas malý šroubovák, plochý i křížový – asi všichni máme nějaký takový doma, ale zde zdůrazňuju to „malý“. Nebo si rovnou vezměte celou sadu. Hodí se vám i plochá pinzeta. Nekupujte si nejlevnější z obyčejného plechu, u nich se snadno stane, že se ohnou a nedrží a jsou pak na vyhození. A pokud nemáte oči jako ostříž, oceníte lupu.

![040-1.jpeg](images/00061.jpeg)

Další nezbytná věc jsou malé kleště, ideálně dvoje – jedny štípačky, jedny „obyčejné“. Po čase přijdete na to, že se vám budou hodit i kleště pro odizolování kabelů. Teď to ještě nezbytné není.

Co nezbytné je, to je multimetr. Kdysi se prodával krásný měřicí přístroj, jmenoval se Avomet a byl nehorázně drahý. Dnes si můžete koupit taky drahé meřicí přístroje, ale ze začátku vám naprosto bez problémů postačí digitální multimetr, který najdete v každém hobbymarketu. Multimetr je zařízení, které vám umožňuje měřit napětí, proud, odpor, a někdy i další veličiny. Multimetr je nezbytný, protože, jak se říká, bez měření není vědění! Sice existují způsoby, jak si podobná měřidla vyrobit či nahradit, ale do začátku je lepší si jedno prostě koupit.

![040-2.jpeg](images/00063.jpeg)

CC-BY-SA, autor André Karwath

Když už budete v tom hobbymarketu, kupte si i takové plastové krabičky, které se prodávají na různé šroubky a drobné věci, nebo kufřík s přihrádkami. Do nich si můžete dávat součástky, které se vám nebudou válet všude možně, nebudou se vám ztrácet a nešlápnete na ně.

![041-1.jpeg](images/00066.jpeg)

Aby bylo vůbec co měřit, potřebujete zdroj. My naštěstí budeme pracovat s elektronikou, která si vystačí s nízkým napětím pěti voltů. Je několik možných způsobů, jak toto napětí získat. Můžete si koupit laboratorní zdroj, ale ten stojí nemalé peníze. Můžete použít plochou baterii nebo tři monočlánky – ty dohromady dají jen 4,5 V, ale to většinou stačí. Na druhou stranu jsou tyto baterie velmi nepraktické, protože se po čase vybijí a můžete je zahodit. Nejvhodnější způsob, který vám doporučím, je použít nabíječku, která má konektor USB. USB totiž používá právě těch 5 voltů, takže nemusíme řešit stabilizaci napětí, zároveň dává i dostatečně velký proud, s nímž můžeme použít i některé náročné komponenty, jako displeje nebo bezdrátové komunikační moduly. Já používám přesně takový adaptér, a k němu speciální nástavec do nepájivého kontaktního pole. Další možnost, trochu nouzová, je použít Arduino nebo Raspberry a brát si napětí z něj.

![041-2.jpeg](images/00068.jpeg)

Všimněte si, že jsem nezmínil páječku. Zatím ji nepotřebujete, základní zapojení si postavíte i bez ní. Až jednou přijde doba, kdy se bez ní neobejdete, tak vám doporučím – nekupujte si pistolovou trafopáječku, kupte si takovou, kde je stojánek a regulace teploty. Nemusí to stát majlant, nejlevnější stačí. A když už jsme u toho: ten přístroj je _páječka_, ačkoli tomu kdekdo říká _pájka_. _Pájka_ je ve skutečnosti ta kovová slitina, kterou se letuje, čili pájí, a té se lidově říká _cín_, i když cín je jen jedna ze složek…

![042-1.jpeg](images/00070.jpeg)

To je opravdu všechno. S tímhle vybavením se můžete pustit do objevování tajů elektřiny, elektroniky, mikroelektroniky, číslicové techniky – jak chcete… Teď už stačí jen nakoupit součástky.