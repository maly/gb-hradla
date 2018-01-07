## 10.1 Obrácená logika {#10-1-obr-cen-logika}

Je hezké, že LED svítí, když je fotorezistor osvícen, ale co když to chcete obráceně, tedy aby se LED rozsvítila tím víc, čím je větší tma? To bude užitečnější, že?

Jak na to? Vlastně potřebujete, aby větší množství světla znamenalo menší napětí na diodě… Použijte k tomu známý rezistorový dělič:

Ve tmě je odpor fotorezistoru R1 velký, takže proud teče přes rezistor R2 do LED a ta svítí. Pokud na fotorezistor posvítíte, jeho odpor klesne, víc proudu poteče přes něj do země, napětí na LED tak poklesne…

![117-2.png](images/000243.png)

Jak velký by měl být rezistor R2? To si můžete spočítat podle odporu fotorezistoru R1 v závislosti na osvětlení. Nejjednodušší je změřit si odpor fotorezistoru ve tmě a za osvětlení. U mého to bylo zhruba 20 kΩ ve tmě a 200 Ω při přímém osvětlení. Pak jsem si nasimuloval „šero“, tedy úroveň, při níž bych chtěl, aby se LED rozsvítila. Bylo to okolo 10 kΩ.

Teď už stačí spočítat dělič napětí tak, aby při „šeru“ byly na diodě právě 2 volty (to je hranice rozsvěcení pro červené LED, pamatujete?) Pokud to celé napájím pěti volty, tak musím zvolit R2 tak velký, aby při R1 = 10 000 bylo napětí 2 V.

Vzorec si jistě pamatujete – U1 = U . (R1 / Rx), kde Rx = R1 + R2\. Po dosazení: 2 = 5 . (10 000 / (10 000 + R2))

Po úpravách: R2 = (U × R1 / U1) – R1

Vychází mi 15 kΩ. Vám taky? S rezistorem R2 o velikosti 15k tedy budou „za šera“ na LED dva volty, a LED začne svítit. Teda – teoreticky. Můžete si zkusit přijít na důvod, proč to zpochybňuju, za chvíli se k tomu vrátím.

![118-1.png](images/000251.png)

V praxi bych udělal ještě jednu úpravu: na místě R2 bych použil nastavitelný rezistor – tedy potenciometr, nebo menší variantu: trimr.