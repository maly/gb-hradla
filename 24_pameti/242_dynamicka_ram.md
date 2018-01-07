## 24.2 Dynamická RAM {#24-2-dynamick-ram}

V osmibitových počítačích byly běžné kapacity pamětí v řádech desítek kilobajtů. Dnes už není problém sehnat statické RAM, které mají kapacitu klidně 128 kB (128k × 8) nebo větší, ovšem na začátku 80\. let to tak snadné nebylo.

Statické paměti, tedy takové, které ukládají data v klopných obvodech, jsou sice hodně rychlé, ale mají zásadní nevýhodu: jsou drahé. Na plochu čipu se vejde poměrně malá kapacita, takže tehdejší technologie byly omezené. Výrobci hledali způsob, jak kapacitu polovodičové paměti zvýšit, a nakonec přišli s dynamickou RAM.

Dynamická RAM nevyužívá klopný obvod, vystačí si místo toho s jediným tranzistorem MOSFET. Informace je uložena v kondenzátoru. Ten vzniká jako vedlejší efekt izolované řídicí elektrody tranzistoru a jeho kapacita je extrémně malá.

![300-1.png](images/000258.png)

Výhoda je jasná: na plochu, kam se vejde jeden klopný obvod statické paměti RAM, se u dynamických vejde násobně víc paměťových buněk.

Nevýhody to má dvě. Zaprvé: při každém čtení se data vymažou. To řeší řídicí obvod paměti, který při čtení uloží data do vyrovnávací paměti a z ní je rovnou zapíše zpět. Zadruhé: náboj se samovolně vybíjí.

Druhý problém je podstatnější. Řeší se tak, že se neustále celá paměť postupně čte. Při čtení se zapisují data zpět, a tím se náboj obnovuje (Refresh).

Výsledkem tohoto tanečku je, že paměť potřebuje speciální obvody, které se starají o to, aby byla neustále čtena, a že v důsledku toho všeho je o něco pomalejší než statická RAM.

Asi by takovou věc nikdo nepoužíval, nebýt toho, že takové paměti jsou v porovnání cena / kapacita mnohem výhodnější než SRAM.

Běžné osmibitové počítače v 80\. letech používaly právě dynamické RAM – díky jejich nízké ceně mohly být stroje vybavené klidně kapacitou 64 kB, i víc. Nižší rychlost nevadila, ony tehdejší procesory nebyly taky bůhvíjak rychlé, tak rychlost pamětí stačila.

V moderních počítačích se používají vylepšené paměti DRAM – SDRAM a DDR SDRAM, které mají gigabitové kapacity a většinou mívají i obvod automatického obnovování (autorefresh). Problém s rychlostí se řeší pomocí kombinace DRAM a rychlé statické RAM jako cache.