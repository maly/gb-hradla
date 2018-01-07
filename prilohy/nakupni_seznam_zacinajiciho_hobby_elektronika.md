## Nákupní seznam začínajícího hobby elektronika {#n-kupn-seznam-za-naj-c-ho-hobby-elektronika}

• Nepájivé kontaktní pole (Breadboard)

• Propojovací vodiče (Dupont wires, male-to-male wires, breadboard wires, jumper wires). Kromě variant „M-M„ (na obou koncích vodiče) nakupte i variantu M-F (male-female, na jednom konci zdířka, na druhém vodič).

• Napájecí modul pro kontaktní pole.

• Napájecí zdroj 5 V / 2 A s USB výstupem.

• Napájecí zdroj 7-12 V / 1,5 A. Pokud koupíte s možností přepínání napětí, bude to lepší.

• Měřicí přístroj. Do začátku stačí ten nejlevnější univerzální, ale je to nutnost! Bez měření není vědění!

• Nářadí: Šroubovák křížový i plochý. Pinzeta. Ostrý nůž (ulamovací je dobrý, já si pořídil lékařský skalpel – surgical scalpel). Kleště štípačky.

• LED. Aspoň deset, různé barvy, budou se hodit. Kupujte ty s průměrem pouzdra 5 mm.

• Sedmisegmentovky (7-segment LED display). Kupte si jich třeba pět, zvolte typ „se společnou katodou„ (common cathode). Na barvě ani velikosti nezáleží. Pro pokusy zvolte spíš sedmisegmentovky samostatné, k Arduinu a jiné elektronice kupte spíš hotový modul (LED display module driver, LED display module SPI apod.).

• Rezistory (Resistor). Do začátku si kupte klidně ty nejlevnější. Kupte hodnoty 220R, 330R, 470R, 1K, 2K2, 3K3, 4K7, 6K8, 10K, 22K, 68K, 100K a 1M. Od těch nižších hodnot doporučuju třeba 10 kusů od každé (220R vezměte klidně 20), od 10K výše vezměte pět kousků. Později si pořiďte třeba kompletní řadu E6.

• Kondenzátory (Capacitor). Vezměte keramické 33 pF a 100 nF, od každé hodnoty deset kousků. Vezměte elektrolytické 1µF, 4,7 µF a 10 µF.

• Diody (Diode). 1N4004 / 1N4007 je taková „vanilla diode„, standardní křemíková usměrňovací dioda, kterou použijete do různých konstrukcí, protože snese i velká napětí. Dále 1N4148, což je „dioda první volby„ pro zpracování signálů (je rychlá), a k tomu i 1N5817 (nebo 1N5818, 1N5819) – rychlá Schottkyho dioda s nízkým úbytkem napětí.

• Tranzistory (Transistor). Kupte si jeden NPN a jeden PNP typ, třeba BC337 (NPN) a BC557 (PNP), od každého třeba 10 kusů. Popřípadě můžete koupit typ 2N3904 (NPN) / 2N3906 (PNP). Pro buzení zátěží si kupte nějaký výkonový, třeba TIP120, a výkonový MOSFET, např. FQP30N06L.

• Integrované obvody (IC, integrated circuit):

• Standardní hradla TTL (TTL gates): 7400 (4x NAND), 7402 (4x NOR), 7486 (4x XOR), 7404 (6x invertor), 7414 (6x invertor se Schmittovým klopným obvodem), 7405 (6x invertor s otevřeným kolektorem), 7408 (4x AND). Od každého typu vezměte tak pět kousků. Volte řadu HCT (74HCT00, …) popřípadě ALS.

• Komplexnější obvody TTL: 7474 (2x klopný obvod D), 7475 (2x 2bit latch), 7490 (4bitový desítkový čítač), 7493 (4bitový binární čítač), 74138 (dekodér 1-z-8), 74595 (8bitový posuvný registr/buffer SIPO), 74162 (8bitový posuvný registr PISO).

• Sériové paměti: 24C01 (sériová EEPROM 128 byte, I2C), 23LC512 (SPI sériová SRAM).

• Arduino Uno. Pro začátečníka nezbytnost, a doporučím: pokud si kupujete své první, kupte si originální od distributora. Některé kusy levných klonů vykazují podivné chyby, které by vás mátly.

• Moduly, breakouty. Tady nezbyde než sáhnout po čínských prodejcích a online obchodech, v českých kamenných nejspíš štěstí mít nebudete. Na druhou stranu právě tyto moduly jsou často velmi zajímavé. Nemusíte kupovat všechno, ale něco z toho pro vás bude určitě užitečné.

• HC-SR04. Ultrazvukový měřič vzdálenosti. (Ultrasonic range detector).

• Senzor vlhkosti půdy (Moisture soil sensor).

• PIR senzor (PIR motion detector).

• Sedmisegmentový displej pro Arduino (7segment LED display Arduino module). Zkuste klíčová slova MAX7219 nebo TM1638.

• Teploměr LM75A (LM75A module, LM75A breakout).

• Vlhkoměr DHT22 (DHT22 module, DHT22 breakout).

• Vlhkoměr SHT30 (SHT30 module) – o něco dražší než předchozí, ale přesnější a se standardním rozhraním.

• Barometr BMP180 (BMP180 module).

• Bezdrátové moduly 433 MHz (433 MHz transmitter, 433 MHz receiver; with antenna).

• Bezdrátový komunikační modul nRF24L01+. Alespoň dva. Kupte k nim i redukci na 5 V (nrf24l01 adapter).

• Alfanumerický displej 16 znaků / 2 řádky (1602 display LED).

• Redukci k tomuto displeji na I2C (1602 I2C expander).

• OLED displej 128 × 64 (OLED display module 128 × 64).

• Joystick (Joystick module).

• Rotační enkodér (rotary encoder module).

• NodeMCU To pokud budete chtít trošku vážněji experimentovat s WiFi. Je to deska koncepčně podobná Arduinu, můžete k ní připojovat leccos, cena není vysoká, a programovat to lze jak z Arduino IDE, tak třeba v MicroPythonu.
