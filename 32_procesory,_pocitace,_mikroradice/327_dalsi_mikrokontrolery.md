## 32.7 Další mikrokontroléry {#32-7-dal-mikrokontrol-ry}

Atmel AVR je velmi široká rodina osmibitových mikrokontrolérů, která zahrnuje maličké obvody ATtiny s pár kilobajty FLASH, často s pouhými osmi vývody, a na druhé straně spektra jsou obrovské čipy s 256 kB FLASH, 8 kB RAM a až 86 datovými piny. Řada AVR má i pokračovatele, AVR32, což je 32bitová architektura, ovšem ta už není tak rozšířená.

Důvodem je to, že v oblasti 32bitových mikrokontrolérů naprosto dominují procesory a mikrokontroléry, založené na jádru ARM.

### 32.7.1 ARM {#32-7-1-arm}

Firma Acorn, která se na začátku 80\. let proslavila díky výrobě počítače BBC Micro, zachytila včas vlnu inovací, a pro svůj nový počítač Archimedes použila vlastní 32bitový procesor, který pojmenovala Acorn RISC Machine, tedy ARM. Na tehdejší dobu šlo o velmi rychlé a výkonné procesory s architekturou RISC.

Procesory ARM nakonec nezůstaly jen doménou jedné značky jednoho výrobce. Vývoj tohoto procesoru převzal holding ARM Holdings, který zvolil šťastný obchodní model: Soustředí se na vývoj, a vyvinuté modely prodává výrobcům jako duševní vlastnictví. Výrobci tedy nemusí vyvíjet vlastní jádra, namísto toho se mohou soustředit na jiné věci, a mají jistotu, že jejich zařízení „s jádrem ARM“ bude mít dostatečnou podporu ze strany softwarových vývojářů. V roce 2013 byl ARM nejpočetnější architekturou na světě a zhruba 60 % všech mobilních zařízení obsahovalo nějaký čip s jádrem ARM.

V současnosti se používají nejčastěji architektury ARMv6, ARMv7, ARMv8 s jádry Cortex.

Tato jádra lze nalézt i v mikrokontrolerech. Typickým zástupcem mohou být mikrokontroléry z řady STM32 od výrobce ST (pro amatérské použití jsou dostupné kity Nucleo) nebo NXP čipy LPC.

### 32.7.2 PIC {#32-7-2-pic}

Velmi bohatou historii jednočipů tvoří firma Microchip se svou řadou PIC. Tyto mikrokontroléry byly dlouhá léta nejdostupnějšími jednočipy a prakticky až do nástupu rodiny AVR dominovaly v amatérských konstrukcích. Technicky jsou jejich možnosti srovnatelné s obvody ARM, ovšem programátoři je nemají moc rádi, protože jejich instrukční sada je někdy zvláštní.

### 32.7.3 8051/8052 {#32-7-3-8051-8052}

Ani Intel nemohl stát stranou. Poté, co vyvinul a úspěšně nabídl řadu 8048 (hned několik modelů, co se lišily podle velikosti a typu paměti) přišel s řadou 8051/8052\. I tato řada dodneška žije a používá se v nejrůznějších mikrokontrolérech. Jádro 8051 se u různých výrobců dočkalo vylepšení či zrychlení, a i přes některé podivnosti a nectnosti, jaké toto jádro má, zůstává dodnes používané. Jeho velkou výhodou totiž je, že jej zná velké množství vývojářů a existuje dostatek vývojářských nástrojů.
