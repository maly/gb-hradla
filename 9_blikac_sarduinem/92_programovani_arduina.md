## 9.2 Programování Arduina {#9-2-programov-n-arduina}

Aby Arduino k něčemu bylo, musí v něm být nějaký program. K programování se používá nástroj, který se trochu honosně jmenuje Arduino IDE – ve skutečnosti jde o textový editor, k němuž je přibalený kompiler pro procesory Atmel AVR a knihovny. Na druhou stranu stačí stáhnout si tento nástroj, propojit Arduino s počítačem přes kabel – a fungujete.

Arduino IDE si stáhnete ze stránek [Arduino.cc](http://Arduino.cc) pro všechny tři hlavní OS – Windows, Linux i macOS.

![109-1.png](images/000276.png)

Udělejte to.

Ne, zcela vážně: Vezměte Arduino Uno a propojte ho s počítačem. Hned teď. Originální Arduino nebude vyžadovat žádné ovladače, respektive si je stáhne. Problém může být s neoriginálními Arduiny, ty vyžadují na macOS nebo na starších Windows (7, 8, 8.1) instalaci ovladačů.

Máte? Stáhněte si Arduino IDE, rozbalte (nemusí se instalovat) a spusťte.

Nejdřív jděte do menu Tools, česky Nástroje, tam vyberte podmenu Board – Vývojová deska, a v ní zvolte položku „Arduino / Genuino Uno“. Tedy samozřejmě předpokládám, že máte Arduino Uno, nebo jeho klon. Druhý krok je opět v menu Tools – Nástroje, položka Port. Pokud máte Arduino připojené, měli byste jej vidět v nabídce. Na Windows bude mít označení COMxx (xx je nějaké číslo, klidně COM2, ale i COM37, je to opravdu libovolné). Na Linuxu to bude /dev/tty_něconěco_. Pozor, na Linuxu musí být uživatel, pod nímž je spuštěno Arduino IDE, členem skupiny „dialout“. Na Macu to bude něco jako /dev/ttyusb_něco_.

V menu File je podmenu Examples (česky Soubor – Příklady), a tam naleznete adresář 01 Basics, a v něm příklad, nazvaný Blink. Klikněte na něj, otevře se takzvaný „sketch“ – vlastně zdroják pro Arduino s příponou .ino