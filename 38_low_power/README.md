# 38 Low Power {#38-low-power}

S rozvojem technologií, vznešeně nazývaných „internet věcí“ (IoT, Internet of Things) se do popředí zájmu dostala spousta aspektů. Například bezpečnost, ergonomie, nové technologie pro komunikaci, ale především dvě slůvka: Low Power. Česky hovoříme o nízkoenergetických zařízeních, o zařízeních s malou spotřebou atd. Ale internetem věcí to nezačalo, kdepak. Na počátku těchto snah byly různá přenosná zařízení, od kalkulaček přes rádia až k notebookům, tabletům a smartfonům.

U stolního počítače se s tím lidé nějak smířili. 300 nebo 400 wattů, to už nějak překousnou. Mimochodem, víte, co se s většinou té energie stane? Ano, promění se v teplo. Pokud jste někdy byli v serverovně, tak to znáte. Ostatně i jeden stolní počítač dokáže v malé místnosti slušně zatopit.

Jenže co projde stolnímu počítači, to neprojde notebooku nebo tabletu. Proto přišly na řadu jednak technologie pro zvýšení kapacity baterií, ale také postupy na snížení odběru.

Takových postupů je v zásadě několik. Zaprvé: používat pokud možno CMOS technologii, která má v klidu (to podtrhuju) velmi nízký odběr. Zadruhé: snížit napájecí napětí. 3,3 voltů už je standard, ale lze jít ještě níž. Zatřetí: zpomalit práci.

Jistě si pamatujete, že nejvíc proudu teče obvodem tehdy, když mění svůj stav, když se tranzistory překlápějí. Vyšší hodinový kmitočet znamená tedy i vyšší spotřebu. Moderní procesory i mikrořadiče proto umožňují přepnout hodinovou frekvenci na naprosté minimum, třeba v řádech kilohertzů, nebo se zastavit úplně – takzvané _deep sleep_ módy. Z takového stavu se procesor probudí buď po uplynutí nějaké doby, nebo po příchodu vnějšího impulsu (dotyk displeje, stisknutí tlačítka, příchod dat, …) Poté se procesor přepne na pracovní frekvenci, událost rychle obslouží a zase se uspí.

Technikou uspávání lze odběr snížit i o několik řádů. Pokud třeba měříte venkovní teplotu, asi není potřeba skutečný „real time“ přístup, stačí změřit teplotu jednou za několik minut a údaj někam poslat. Takto může zařízení běžet na jednu baterii i několik let, pokud zvolíte vhodný energeticky nenáročný způsob přenosu dat. _Ne, WiFi není energeticky nenáročný způsob!_

Samozřejmě, uspávání nestačí, když vám teče proud jinudy. Nejčastější příčinou rychlého vybíjení jsou zapomenuté LED – sice mají nízký odběr ve srovnání s jinými zdroji světla, ale i tak je to stále hodně. U low power zařízení je potřeba se s odběrem dostat někam k mikroampérům, a 10 mA, tekoucích LEDkou, je vlastně „hrozně moc“ proudu.

Takové Arduino Micro je docela slušné zařízení, které by se dalo použít pro low power zapojení, jenže obsahuje „power LED“, tedy LEDku, která indikuje, že je zařízení napájené. Pokud tuto LED odstraníte, ušetříte většinu spotřeby.

Dalším místem, kudy protékají cenné miliampéry proudu úplně zbůhdarma, jsou stabilizátory napětí. Pokud nejsou LVDO (Low Voltage Drop Out), popřípadě Ultra LVDO, tak pro svou vlastní činnost spotřebují velké množství energie i v případě, že se žádná energie neodebírá (takzvaný klidový proud).

Klasický stabilizátor 7805, který se používá už desítky let pro stabilizaci napájecího napětí na 5 V, potřebuje na vstupu alespoň 7 voltů a sebere pro svou vlastní potřebu 5 až 8 miliampérů (hledejte v datasheetu parametr, nazvaný Quiescent Current, IQ). Stabilizátor MCP1703 se spokojí s napěťovým rozdílem do 1 V a pro svou potřebu si vezme dva mikroampéry. Stabilizátory z řady TPS783xx mají úbytek napětí okolo 150 mV a vlastní spotřebu 500 nanoampérů.

Samotná spotřeba není jediným faktorem, co ovlivňuje výdrž zařízení na baterie. Důležitým faktorem je i maximální odebíraný proud. Některé bezdrátové technologie a náročnější senzory se sice umí uspat k téměř nulovému odběru, ale po probuzení potřebují velmi velký proud. GSM modul, který se ve vašem mobilním telefonu připojuje k mobilní síti, si v klidu vystačí s mikroampéry. Při komunikaci potřebuje řádově desítky až stovky miliampérů, ale při úvodním připojování, vyhledávání sítě a přihlašování se do ní si vezme až 2 A. Sice jen na krátký okamžik, ale baterie musí být schopna tento prudce zvýšený odběr pokrýt.

Když je baterie starší, tak už nebývá schopna takhle velké proudy dodat. Proto se občas stane, že při navazování spojení nebo při přehlašování k jiné základně vzroste odebíraný proud tolik, že vezme vše, co baterie dává, tím pádem poklesne napětí pod mez, která je pro procesor bezpečná, a zařízení se restartuje. Bohužel se po restartování opět telefon chce přihlásit k síti, opět vzroste spotřeba, a telefon se dostane do série neustálých resetů.

To mimochodem vysvětluje i příčinu toho, proč se úplně vybitý telefon často musí nejprve nějakou dobu nechat nabíjet, než ho lze zapnout: protože nabíječky, zejména ty levnější, nejsou schopné dodat tak velké proudy.

Takové situace se řeší buď používáním úspornějších telekomunikačních metod (bezdrátové spojení v bezlicenčním pásmu 433 / 868 MHz, Sigfox), nebo pomocí kondenzátorů s velkou kapacitou, které jsou schopné krátkodobě dodat velmi veký proud. Ovšem kondenzátory se samovolně vybíjejí, a tak mohou představovat další místo, kudy vám poteče proud a bude zvyšovat odběr.

Zajímavé technologie, které mohou pomoci při napájení nízkopříkonových zařízení, se skrývají pod označením _energy harvesting_. Slouží k získávání energie ze zdrojů, jako je okolní teplota, proudění kapalin, rádiový signál, světlo, otřesy a podobně. Některá zařízení, určená pro voperování do lidského těla, dokáží získávat energii i z krevního cukru. Speciální obvody dokáží i velmi malé množství takto získané energie efektivně zpracovat a uložit do baterií či kondenzátorů.
