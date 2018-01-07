## „Dobré rady nad zlato“ na jednom místě {#dobr-rady-nad-zlato-na-jednom-m-st}

Lékaři mají něco, čemu se říká „lék první volby“. Když přijdete s příznaky třeba bakteriální infekce, tak lékař dřív, než začne zkoumat, který že bakteriální kmen vás nakazil, nasadí takzvané „antibiotikum první volby“, což je takové, které je účinné proti naprosté většině možných bakterií, a velmi pravděpodobně pomůže. Pokud ne, pak je potřeba hledat jiné, specifické řešení. Totéž platí i pro mnoho dalších nemocí: jsou na ně „léky první volby“, které může lékař předepsat, protože je velká pravděpodobnost, že na většinu případů pomůžou.

Zkusil jsem sepsat několik „elektronických léků první volby“. Není to nijak exaktní, jsou to „babské rady“, ale pro návrh prototypu budou stačit.

• Rezistor k LED: pro 5 V logiku dejte 330R, tím nic nezkazíte.

• Pull-up rezistor: dejte 10k, to by mělo pro běžné použití stačit.

• Spínání většího proudu, například pro žárovku: použijte MOSFET-N nebo tranzistory v Darlingtonově zapojení.

• Kde je cívka (motor, elektromagnet), tam je potřeba ochranná dioda!

• Spínání většího napětí: Použijte relé. Nezapomeňte na ochrannou diodu (je tam cívka!) a na buzení přes tranzistor (potřebuje velký proud).

• Pro spínání motorů se bude hodit H-můstek.

• Spousta zajímavých součástek se dělá v malých pouzdrech, která je nutné pájet. Naštěstí existují „breakout“ moduly, kde jsou tyhle součástky s nezbytnou bižuterií už připravené.

• Hradlo OR: můžete udělat montážní s diodami, ideálně Schottkyho.

• Chlazení: Chladit je potřeba zátěž, kterou teče velký proud, popřípadě složité obvody, které pracují na vysokých frekvencích. Empirické pravidlo: když na tom udržíte prst, chladit nemusíte. Typicky bude chlazení potřebovat výkonný stabilizátor, spínací tranzistory pro velké proudy, popřípadě procesor s vysokou frekvencí.

• K napájení integrovaných obvodů připojujte paralelně blokovací kondenzátor 100n, co nejblíž k pouzdru.

• Čím delší vodič, tím nižší frekvence! 10 cm vodič bez problémů přenese i megahertz, 30 cm spíš ne.

• Testujte: obvody skládejte po menších částech, u každé si ověřte, že funguje. Arduino se vám bude hodit jako „testbench“ – snadno nastavíte signály a jejich průběhy a zjistíte výsledek.

• Po zapojení té nejdůležitější části najednou přestává pracovat zbytek? Když má sepnout motor, tak se to celé resetuje? Pravděpodobně málo proudu! Dejte silnější zdroj.

• Některé nárazové odběry můžete pokrýt velkým kondenzátorem (desítky µF) paralelně ke zdroji.

• Měření tepla: pokud tam máte Arduino, tak nejjednodušší je měřit čidlem DS18B20, je levné a je ho všude dost.

• Termistor: Naměřenou teplotu nemusíte přepočítávat na stupně, pokud potřebujete nastavit jen nějaký práh sepnutí. Prostě jen nastavte stejnou teplotu a změřte jeho odpor, resp. napětí na něm.

HRADLA, VOLTY, JEDNOČIPY

Úvod do bastlení

Martin Malý

Vydavatel:

CZ.NIC, z. s. p. o.

Milešovská 5, 130 00 Praha 3

Edice CZ.NIC

www.nic.cz

1\. vydání, Praha 2017

Kniha vyšla jako 16. publikace v Edici CZ.NIC.

E-kniha: Milan Vilímek Jihlavský, Jarní 6, 586 01 Jihlava

© 2017 Martin Malý

Toto autorské dílo podléhá licenci Creative Commons

([creativecommons.org/licenses/by-nd/3.0/cz/](http://creativecommons.org/licenses/by-nd/3.0/cz/)),

a to za předpokladu, že zůstane zachováno označení autora díla a prvního vydavatele díla, sdružení CZ.NIC, z. s. p. o. Dílo může být překládáno a následně šířeno v písemné či elektronické formě na území kteréhokoliv státu.

ISBN 978-80-88168-23-2 (tištěná verze)

ISBN 978-80-88168-24-9 (ve formátu EPUB)

ISBN 978-80-88168-25-6 (ve formátu MOBI)

ISBN 978-80-88168-26-3 (ve formátu PDF)
