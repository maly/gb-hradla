## 24.7 Sériové paměti {#24-7-s-riov-pam-ti}

Až dosud jsem hovořil o klasických pamětech RAM, ROM atd. Takové paměti mají N adresových vstupů A0-An, M datových vývodů D0-Dm, kapacitu 2N adres krát 2M bitů, a pro větší kapacitu logicky potřebujete větší pouzdro s větším počtem vývodů. Tyto paměti mají totiž _paralelní rozhraní_. Jestli si pamatujete, co jsme si říkali v kapitole o rozhraních, tak totéž v bledě modrém platí i o těchto pamětech: nesnesou příliš dlouhé datové/adresové vedení, rychlost přenosu dat je teoreticky neomezená, a lze je připojovat snadno přímo na sběrnici procesoru.

To je také mimochodem odpověď na to, proč mají paměťové moduly do PC tolik pinů – kvůli rychlosti používají paralelní přenos, takže třeba moduly DDR3 DIMM používají 240 vývodů…

Pro malé systémy s jednočipovými řadiči se jako vhodná alternativa ukázaly sériové paměti. Technicky jde o stejnou paměť RAM, EEPROM, FLASH, ale používá sériové rozhraní, takže se vejde klidně do pouzdra s osmi vývody.

Dovolte tabulku:

| Rozhraní / Typ | RAM | EEPROM | FLASH |
| --- | --- | --- | --- |
| SPI | 23xx | 25xx | 25Fxx |
| I2C | 47xx (SRAM+EEPROM) | 24xx |  |
| Microwire |  | 93xx |  |

Shrnul jsem sériové paměti podle typu a rozhraní. Třetí do sbírky, Microwire, je vlastně podmnožina SPI (umožňuje pouze SPI Mode 0 – viz popis SPI).

Asi největší portfolio těchto pamětí má v době psaní knihy společnost Microchip. Podržím se tedy jejich rozdělení a značení.

Sériové paměti se značí dvojčíslím, které udává typ paměti a rozhraní, viz tabulka, pak jedním či více písmeny, která udávají podtyp, popř. napájecí napětí, a opět číslem, které udává kapacitu. Kapacita se nejčastěji udává v kilo_bitech_, takže si nezapomeňte číslo podělit osmi, abyste dostali kapacitu v _kilobajtech_.

Písmena jsou nejčastěji L, C nebo LC (standardní paměti s napájením 2,5 – 5 V), AA (nízkonapěťové 1,8 – 5 V), A (s napětím 1,7 – 2,2 V). U pamětí pro I2C se setkáte i s písmenem F, které znamená, že paměť umí pracovat i s přenosovou frekvencí 1 MHz (bez F používají většinou 400 kHz).

Čísla udávající kapacitu mají tento význam (u EEPROM a SRAM):

| Kapacita (kilobit) | Kapacita (kilobajt) | Kód |
| --- | --- | --- |
| 1 | 0,125 (128 byte) | xx01 |
| 2 | 0,25 (256 byte) | xx02 |
| 4 | 0,5 (512 byte) | xx04 |
| 8 | 1 | xx08 |
| 16 | 2 | xx16 |
| 32 | 4 | xx32 |
| 64 | 8 | xx64 |
| 128 | 16 | xx128 |
| 256 | 32 | xx256 |
| 512 | 64 | xx512 |
| 1024 | 128 | xx1024, xx1025, xx1026, xxM01 |

U sériových FLASH se pohybujeme v trochu jiných dimenzích:

| Kapacita (kilobit) | Kapacita (kilobajt) | Kódh |
| --- | --- | --- |
| 512 | 64 | xxF512 |
| 1024 | 128 | xxF010 |
| 2048 | 256 | xxF020 |
| 4096 | 512 | xxF040 |
| 8196 | 1024 (1 MB) | xxF080 |
| 16384 | 2048 (2 MB) | xxF016 |
| 32768 | 4096 (4 MB) | xxF032 |
| 65536 | 8192 (8 MB) | xxF064 |

Paměti s větší kapacitou a rozhraním SPI mají většinou i možnost využít dvou nebo čtyř datových vodičů najednou (SDI, SQI) – kvůli zrychlení přenosu.

Sériové paměti jsou zároveň poměrně levné, podle typu a kapacity okolo 50-90 Kč. Díky pouzdru s osmi vývody je většinou nebývá problém sehnat i v provedení DIP, tedy naprosto ideální pro amatérské použití.

Zásadní nevýhoda je, že to nejsou „jednoduché paměti“, kam přivedete adresu po sběrnici a dostanete „v reálném čase“ data. Vždy musíte udělat několik kroků, a i v tom nejjednodušším případě čtení dat musíte poslat do paměti požadovanou adresu, a pak přečíst data. Vhodné zařízení pro komunikaci je tedy mikrokontrolér…

Ale dosti planých řečí, pojďme si to zkusit zapojit.

##### 25 Sériová paměť prakticky {#25-s-riov-pam-prakticky}
