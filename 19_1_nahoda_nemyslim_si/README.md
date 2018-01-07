# 19\. 1 Náhoda? Nemyslím si… {#19-1-n-hoda-nemysl-m-si}

Můžeme použít tu nejlepší náhodu, co známe, a měřit rozpad radionuklidů. Což je samozřejmě řešení první volby, pokud máte doma radionuklidy a detektory částic. Ti, kteří nemají, pokud se snad takoví najdou, musí řešit problém jinak.

Další možnost je vzorkování šumu. Ale řekněme si upřímně a na rovinu: Zas tak matematicky dokonale náhodné to být nemusí. My totiž můžeme využít toho, že naprosto náhodný je okamžik, kdy člověk to tlačítko stiskne. To nelze předem odhadnout. Takže stačí na vstup D pustit pravidelně se měnící signál 0 – 1 – 0 – 1, takový, jaký máme například z našeho blikače, a je to.

No jo, zní ale námitka – co když obsluha zná frekvenci a naučí se mačkat pravidelně v témže rytmu? To pak budou padat samé hlavy, nebo samí orli?

Co s tím? No, zase využijeme toho, že člověk není stroj, a zvýšíme frekvenci kmitů. Když jich bude třeba tisíc za sekundu, tak mačkat tlačítko v tak přesných intervalech, aby to vždycky vyšlo ve stejné chvíli, zvládne jen Chuck Norris. Pro nás ostatní to bude stačit.

Použijeme tedy zapojení blikače, které lehce upravíme tak, aby blikalo rychleji. Máme tři možnosti:

1.

Zmenšit kapacitu kondenzátoru.

2.

Zmenšit odpor rezistoru.

3.

Udělat obojí.

V kapitole o astabilních klopných obvodech jsem ukazoval vzorec f = 1 / (2,2RC). Pokud tedy chci blikání okolo 1 kHz, musí platit, že 1 / (2,2RC) = 1000, tedy 2,2RC = 0,001, tedy RC = 0,00045.