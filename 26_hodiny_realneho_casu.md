# 26 Hodiny reálného času {#26-hodiny-re-ln-ho-asu}

_V EduShieldu je použitý speciální druh paměti DS1307 – má pouhých 64 bajtů, a navíc se v prvních osmi bajtech údaje mění…_ Což takhle zní jako pěkná hloupost, že? Ve skutečnosti je to tak, že v prvních osmi bajtech je uložena informace o aktuálním čase a datu…

Obvod DS1307 je označován jako RTC – Real Time Clock (hodiny reálného času). Obvod se připojuje k zařízení opět pomocí sběrnice I2C a funguje úplně stejně jako výše zmíněná paměť – nabízí 64 adres pro uložení dat. Ovšem prvních osm bajtů má speciální význam:

![tabulka-str-369.png](../images/000204.png)

Při čtení z adresy 00 přečtete vždy sekundy. Nejvyšší bit na adrese 0 se jmenuje Clock Halt, a pokud do něj zapíšete 1, hodiny budou stát. Jakmile do něj zapíšete 0, hodiny se rozběhnou.

Na adrese 1 jsou minuty, na adrese 2 hodiny (bit 6 přepíná mezi 12 a 24hodinovým režimem).

Adresa 3 říká, jaký je den v týdnu, adresa 4 udává den v měsíci, adresa 5 měsíc a na adrese 6 jsou roky. Adresa 7 obsahuje řídicí slovo, kterým můžete nastavit funkci budíku. Bližší informace najdete, jak jinak, v datasheetu.

Zvídavé mozky už chystají otázku: _A jak to, že ten obvod ví, kolikátého dneska je?_

Odpověď je jednoduchá: Při prvním zapojení do něj zapíšete aktuální datum a čas. Takhle jednoduché to je.

_Ovšem_, ptá se zvídavec dál: _Jak je možné, že si to ten obvod pamatuje i když vypnu proud? Nebo to musím při každém zapnutí nastavit?_

Milé zvídavé uklidním: Žádný zázrak se neděje. K obvodu lze připojit malý článek, baterii, která vydrží takový obvod napájet několik let, a zároveň je u něj připojený krystal, který kmitá na frekvenci 32,768 kHz, a tím udržuje přesný čas. Tedy, zas tak úplně přesný není, může se s reálným rozejít i o několik minut za měsíc, ale na většinu běžných aplikací to stačí. Pokud potřebujete vyšší přesnost, použijte obvod DS3231, který se posune maximálně o několik minut ročně, a popřípadě můžete ještě hodiny pravidelně seřizovat vnějším signálem, třeba z GPS nebo z internetu.

Schéma a zdrojový kód najdete na [eknh.cz/rtc](https://eknh.cz/rtc)

##### 27 Paměťové karty {#27-pam-ov-karty}
