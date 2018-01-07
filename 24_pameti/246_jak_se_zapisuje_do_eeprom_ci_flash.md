## 24.6 Jak se zapisuje do EEPROM či FLASH? {#24-6-jak-se-zapisuje-do-eeprom-i-flash}

Paměti EEPROM (a také FLASH) jsou „elektricky mazatelné a přepisovatelné“. Jak se to dělá?

Paměť EEPROM má, podobně jako RAM, signál /WE – Write Enable, který slouží k zápisu dat. Můžete zapsat až 64 bajtů naráz. Paměť si je uloží do vnitřních registrů, a pak je začne zapisovat do paměťových buněk. Zápis je poměrně pomalý, může trvat podle typu paměti až 10 milisekund. Když budeme zapisovat vždy plný počet 64 bajtů naráz, a každý zápis bude trvat těch maximálních 10 ms, zapíšeme za jednu sekundu něco přes jeden kilobajt. U osmi kilobytů (28C64) to bude ještě snesitelné, ale u 128k paměti (28C010) budeme zapisovat přes 10 sekund (tato paměť dokáže zapsat v jednom cyklu až 128 bajtů).

Na druhou stranu dlouhá zápisová doba nevadí, protože paměť by neměla být často přepisována. Ostatně výrobce uvádí zaručený počet přepisů 100 000 – pokud ji přepíšete víckrát, není zaručeno, že ještě bude fungovat.

Ovšem představte si, co by se stalo, kdyby nějaký program „zdivočel“ a začal přepisovat paměť EEPROM. To by nebylo vůbec hezké. Proto mají EEPROM možnost ochrany paměti, a to jak hardwarovou, tak softwarovou. Pomocí speciální posloupnosti zápisů, která je u každé paměti jiná, se paměť „zablokuje“ nebo „odblokuje“ pro zápis.

Příklad: U EEPROM AT28C64B (8k × 8) se softwarová ochrana zapne takto:

1. zapíšete 0xAA na adresu 0x1555

2. zapíšete 0x55 na adresu 0x0AAA

3. zapíšete 0xA0 na adresu 0x1555

Poté máte možnost zapsat až 64 bajtů, a poté je paměť „uzamčena“. Víc podrobností najdete, jak jinak, v datasheetu.

U pamětí FLASH je situace obdobná, ovšem zápis je výrazně rychlejší. Paměť FLASH je typicky rozdělena do sektorů, např. po 4 kB (vezměme si jako příklad paměti 39F010 / 39F020, 39F040), a vždy před tím, než do daného sektoru začnete zapisovat, musíte si jej předem smazat. Smazání sektoru zabere zhruba 18 milisekund, smazání celé paměti zabere 70 ms.

Jak se takové smazání zařídí? Samozřejmě vás asi nepřekvapí, že se zapisují nějaké dané hodnoty na určité adresy. Pokud takové zápisy přijdou v přesně daném pořadí, spustí se daná operace. Například smazání celé paměti spustí šestikroková sekvence zápisů:

1. 0xAA na 0x5555

2. 0x55 na 0x2AAA

3. 0x80 na 0x5555

4. 0xAA na 0x5555

5. 0x55 na 0x2AAA

6. 0x10 na 0x5555

FLASH mívají ještě menší počet cyklů smazání/zápis než EEPROM. Proto je potřeba u aplikací, které intenzivně zapisují, s tímto faktorem počítat a přizpůsobit mu styl zápisu, aby se rovnoměrně využívaly všechny buňky (např. FAT nebude moc vhodný způsob, protože neúměrně často přepisuje první sektory). U některých aplikací bude lépe z téhož důvodu sáhnout po NVRAM – tedy po takových pamětech, které jsou typu SRAM a jsou zálohované baterií.
