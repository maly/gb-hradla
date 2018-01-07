## 13.10 Pomalé tlačítko {#13-10-pomal-tla-tko}

Představte si situaci, kdy máte nějaký obvod, startovaný přepínačem, a chcete, aby nastartoval ne hned, ale až když je přepínač přepnutý nějakou chvíli, třeba dvě sekundy. Potřebujete tak eliminovat náhodné neúmyslné stisknutí. Obsluha musí přepínač přepnout a držet nějakou dobu přepnuté.

Jak na to? V první řadě přemýšlejte: jaká součástka má nějakou souvislost s časem? Co můžeme použít, když potřebujeme na něco počkat?

Odpověď je: Kondenzátor. Ten se nabíjí, a napětí na něm pomalu roste s tím, jak se nabíjí. Takže jej necháme pomalu přes rezistor nabíjet, a jakmile hodnota napětí překročí 2 volty (což je rozhodovací hranice pro logickou 1), tak sepneme obvod – pro náš test třeba LED.

Jak zajistíte to přepnutí? Dáte za sebe dva invertory, to je takový jednoduchý trik. Na výstupu bude stejná logická hodnota jako na vstupu, ale „ošetřená“ – tedy logická 1 bude téměř napájecí napětí, ne usmolené 2 volty.

No a přepnutí přepínače do druhé polohy vybije kondenzátor k zemi. Nějak takto.

![150-1.png](images/000125.png)

Čím větší odpor na vstupu a kapacita kondenzátoru, tím delší bude prodleva. Když zvolíte rezistor kolem 100 kΩ a kondenzátor třeba 10 µF, tak bude prodleva necelou sekundu. Jenže!

Jenže záleží hodně na typu invertoru. 74ALS04 se bude chovat jinak než třeba 74HCT04, a svými parametry bude ovlivňovat čas. Doporučuju opět metodu pokus-omyl.

Ale ještě počkejte a zamyslete se… Když píšu, že se kondenzátor pomalu nabíjí od 0, co to znamená? No, že napětí roste plynule, a v určitou chvíli se ocitne v _zakázaném pásmu_ mezi 0,8 a 2 V. V takovou chvíli může invertor dělat naprosto cokoli, klidně se může rozkmitat, nebo se může rovnou přepnout. Lze to nějak vyřešit?

No, kondenzátor těžko přesvědčíte, aby se po 0,8 V nabil hned na 2 V. Musíte to vyřešit na straně toho invertoru. Naštěstí je řešení docela jednoduché, a říká se mu