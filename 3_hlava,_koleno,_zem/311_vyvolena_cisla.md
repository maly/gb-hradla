## 3.11 Vyvolená čísla {#3-11-vyvolen-sla}

Dobrá, a teď prakticky: Co když mi výpočtem vyjde, že potřebuju rezistor 283 ohmů? Vyrábí někdo takovou hodnotu?

No, budete se možná divit, ale ne. Pro rezistory, kondenzátory a součástky se ujalo, že se vyrábí v určité řadě a toleranci, a tyto řady se značí E6, E12, E24, E48, … V každé řadě je mezi hodnotami 1 a 10 definováno 6 (12, 24, 48, …) hodnot pomocí takzvaných _vyvolených čísel_. To jsou čísla, která jsou zvolená tak, že poměr mezi sousedními členy je přibližně stejný.

Pro řadu E6 to jsou následující hodnoty: 1,0 – 1,5 – 2,2 – 3,3 – 4,7 – 6,8

Zkuste si to sami:

• 1 · 1,5 = 1,5

• 1,5 · 1,5 ≈ 2,2

• 2,2 · 1,5 ≈ 3,3

• 3,3 · 1,5 ≈ 4,7

• 4,7 · 1,5 ≈ 6,8

Řada E12 má prvky 1,0 – 1,2 – 1,5 – 1,8 – 2,2 – 2,7 – 3,3 – 3,9 – 4,7 – 5,6 – 6,8 – 8,2

Proto píšu o „rezistoru 2K2“ a ne třeba 2K9 – protože součástky se nevyrábějí ve „všech možných“ hodnotách, ale pouze v hodnotách z určitých řad.

Řada E6 zajišťuje, že pro každou zvolenou hodnotu existuje v této řadě _vyvolené číslo_, odlišné maximálně o 20 %. U řady E12 to je 10 %, u řady E24 pak 5 %

V amatérských konstrukcích s číslicovými obvody se nejčastěji setkáte s řadami E6 a E12, které jsou dostatečně přesné pro zamýšlené použití. Málokdy bývá hodnota naprosto kritická – snad s výjimkou časování.

Samozřejmě, dát místo rezistory 330R rezistor 3K3 už je rozdíl o řád, to už se může projevit negativně na funkci, ale nahradit jej například rezistorem 470R ve většině případů nejspíš neudělá problém. (Problém to udělá například v obvodu časovače...)

Každopádně doporučuju udělat si doma zásobu nejčastějších nejpoužívanějších hodnot rezistorů. Pro číslicovou techniku bych volil hodnoty mezi 100R a 100k – především 220R a 330R, které se hodí k LED, pak 1K, 2K2, 4K7, 6K8, 10K, 22K, 68K a 100K.

U kondenzátorů pak 22p, 33p, 100K (= 100 nF), 4M7, 10M (= 10 µF). To je naprostý a nezbytný základ.