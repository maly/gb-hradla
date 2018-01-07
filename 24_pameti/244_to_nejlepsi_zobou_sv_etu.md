## 24.4 To nejlepší z obou světů {#24-4-to-nejlep-z-obou-sv-t}

Máme tedy řadu pamětí ROM, do nichž lze data s určitými omezeními zapisovat, jako do paměti RAM. Jejich nevýhoda je, že jsou pomalejší než RAM. Z druhé strany máme paměti RAM, které jsou rychlé, ale zase po výpadku napájení zapomenou uložená data (jsou volatilní). Z tohoto směru zase přišla snaha výrobců udržet výhody RAM a nějak zajistit, aby výpadek napájení nesmazal zapsaná data, tedy vytvořit takzvanou nonvolatilní RAM (NVRAM). Nejjednodušší způsob je zajistit, aby napájení nikdy nevypadlo – třeba výrobce pamětí Dallas Semiconductors integroval do pouzdra i malou baterii, která fungovala jako záložní. Nevýhoda je jasná – každá baterie se po čase vybije, takže ani tyto paměti neudrží svůj obsah výrazně dlouho.

V posledních letech se na trh dostaly ve větší míře paměti, které využívají pro uložení dat namísto elektrického náboje jiný princip. Paměti FRAM (Ferroelectric RAM) využívají ferroelektrickou vrstvu (feroelektrikum lze, zjednodušeně řečeno, přeměnit na permanentní magnet pomocí elektrického pole). FRAM využívají této vlastnosti a ukládají data tím, že mění polaritu takových látek. Při čtení se nastavuje buňka paměti na 0\. Pokud už předtím byla 0, neděje se nic, pokud předtím byla 1, vznikne krátký puls, který logika vyhodnotí. Další paměti na podobném principu jsou MRAM (Magnetoresistive RAM), kde se při čtení využívá měření elektrického odporu.

Tyto paměti jsou prozatím „to nejlepší z obou světů“. Životnost dat v nich uložených je vyšší než u FLASH a EEPROM, udržují si data i po vypnutí napájecího napětí, zároveň jsou rychlé jako RAM, jsou odolnější vůči radiaci a lze je přepisovat téměř donekonečna (výrobce Texas Instruments udává u svých pamětí řádově 100-1000 bilionů zápisových cyklů). Na druhou stranu mají zatím stále menší kapacitu než FLASH (míněno „na trhu dostupné čipy“) a jsou dražší.

Když si shrneme výhody a nevýhody jednotlivých typů:

FLASH: levné, nonvolatilní (pamatují si i bez napájení), zápis poměrně pomalý, čtení rychlé, nízká spotřeba, ale velmi omezený počet záznamových cyklů (typicky 10 000 – pracuje se ale na vylepšení technologie)

EEPROM: levné, nonvolatilní, zápis pomalejší než u FLASH, čtení rychlé, spotřeba vyšší než FLASH, vyšší počet záznamových cyklů (okolo 100 000). 

RAM: levné, volatilní (potřebují napájení, aby si udržely data), zápis i čtení velmi rychlé, spotřeba nižší než u FLASH, počet zápisů neomezený.

MRAM, FRAM: dražší, nonvolatilní, zápis zhruba stejně rychlý jako u RAM, čtení také, spotřeba se pohybuje mezi RAM a FLASH, počet záznamových cyklů v řádech stovek bilionů.

Praktický tip: Co tedy použít, pokud ve svém zařízení potřebujete ukládat někam třeba naměřená data? Nejlevnější řešení s největší kapacitou nabízí FLASH (tuto technologii využívá třeba SD karta). Na druhou stranu musíte počítat s možnými chybami a ošetřit je, navíc při častějším přepisování dat paměť brzy odejde. Pokud potřebujete často zapisovat a mazat, zvažte použití EEPROM. Nevýhodou je zase vysoká spotřeba a pomalý zápis, takže u zařízení, která chrlí rychle data, budete stejně potřebovat nějakou verzi rychlé paměti RAM, do níž si uložíte data, a pak je najednou zapíšete do trvalejší paměti. Pokud potřebujete často a rychle zapisovat a mít nízkou spotřebu, využijte paměť RAM se záložním napájením. Riziko je, že po čase se i záložní akumulátor vybije a vy na to přijdete třeba až ve chvíli, kdy paměť zapomene data. Pokud potřebujete spojit všechny výhody, tj. nízkou spotřebu, vysokou rychlost zápisu a čtení a dlouhodobé uchování dat bez napájení, zvolte FRAM nebo MRAM. Nevýhodou je cena a malá dostupná kapacita těchto pamětí.
