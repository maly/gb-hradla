## 5.3 Dělič napětí {#5-3-d-li-nap-t}

Když už máme ty rezistory takto zapojené, tak si zkuste změřit opět úbytek napětí na obou rezistorech (tedy mezi body A-B a B-C), pokud bude jejich hodnota různá. Zapište si výsledky:

| Odpor R1 | Odpor R2 | Napětí A-B | Napětí B-C | Napětí A-C | Proud |
| --- | --- | --- | --- | --- | --- |
| 10000 | 10000 | 2,5 | 2,5 | 5 | 0,00025 |
| 1000 | 10000 | 0,45 | 4,55 | 5 | 0,00045 |
| 1000 | 1000 | 2,5 | 2,5 | 5 | 0,0025 |

Co z naměřeného vyplývá? Že pokud jsou odpory obou rezistorů stejné, tak je napětí na nich rovněž stejné. Pokud se liší, je na jednom z nich menší úbytek, na druhém větší. V jakém poměru? Šlo by to spočítat…

Mějme sériové zapojení dvou rezistorů. Už víme, že výsledný odpor je roven součtu odporů obou rezistorů, tedy R1 + R2\. Označme si tento součet Rx. Proud, který teče obvodem, bude tedy I = U / (R1 + R2) =&gt; I = U / Rx. No a napětí na jednotlivých rezistorech (označme si je U1 a U2) bude zase podle Ohmova zákona U = I . R. Tedy: U1 = I . R1 a U2 = I . R2\. Vidíme, že větší úbytek napětí bude na rezistoru s větším odporem.

Když vzorec rozepíšeme, dostaneme podobu U1 = U . (R1 / Rx), U2 = U . (R2 / Rx). Vzorec jde zobecnit pro víc rezistorů: Un = U . (Rn / Rx)
