## 37.2 Převodník napěťových úrovní {#37-2-p-evodn-k-nap-ov-ch-rovn}

Velmi užitečná věc ve chvíli, kdy potřebujete propojit obvody s různou logikou – nejčastěji třeba 5 V Arduino a 3,3 V senzory. Existuje jednoduché zapojení, které dokáže konvertovat logické signály z jedné úrovně do druhé, a potřebuje k tomu pouze jeden tranzistor MOSFET:

![397-1.png](images/000038.png)

LV a HV je nízké (low) a vysoké (high) napájecí napětí, LV1, respektive HV1 jsou vstupy / výstupy v patřičných úrovních. Převodník funguje obousměrně.

[eknh.cz/lcnv](https://eknh.cz/lcnv)

Naštěstí nemusíte sestavovat a pájet převodníky, existují jako hotové moduly, nejčastěji pro čtyři signály, nebo pro osm signálů:

![398-1.jpeg](images/00220.jpeg)![398-2.jpeg](images/00059.jpeg)

Na jedné straně, tam, kde je LV, se připojují signály obvodu 3,3 V, na straně HV se připojují 5 V. LV a GND (resp. HV a GND) slouží k připojení napájecího napětí.

Připojení ESP8266 přes takový převodník je opravdu hračka:

![398-3.png](images/000308.png)

Všimněte si, že modul je zapojený tak, jak byste čekali, tedy RxD na TxD a vice versa, jen je mezi Arduino a ESP vložen převodník úrovní.

Upozornění: Když budete takto zapojené Arduino programovat, pravděpodobně nastane chyba. Důvodem je to, že programování Arduina probíhá přes sériový port, a pokud je na tomtéž sériovém portu připojen jiný obvod, který má tendenci komunikovat (a to ESP8266 má!), tak ruší přenos dat, a programování skončí s chybou. Řešení je v takovémto případě před programováním modul ESP8266 odpojit!

Pro ovládání ESP8266 opět existuje celá řada knihoven, které zapouzdřují příkazy tak, aby práce byla co nejjednodušší.