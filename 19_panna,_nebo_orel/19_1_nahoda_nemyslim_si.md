## 19\. 1 Náhoda? Nemyslím si… {#19-1-n-hoda-nemysl-m-si}

Můžeme použít tu nejlepší náhodu, co známe, a měřit rozpad radionuklidů. Což je samozřejmě řešení první volby, pokud máte doma radionuklidy a detektory částic. Ti, kteří nemají, pokud se snad takoví najdou, musí řešit problém jinak.

Další možnost je vzorkování šumu. Ale řekněme si upřímně a na rovinu: Zas tak matematicky dokonale náhodné to být nemusí. My totiž můžeme využít toho, že _naprosto náhodný_ je okamžik, kdy člověk to tlačítko stiskne. To nelze předem odhadnout. Takže stačí na vstup D pustit pravidelně se měnící signál 0 – 1 – 0 – 1, takový, jaký máme například z našeho blikače, a je to.

No jo, zní ale námitka – co když obsluha zná frekvenci a naučí se mačkat pravidelně v témže rytmu? To pak budou padat samé hlavy, nebo samí orli?

Co s tím? No, zase využijeme toho, že člověk není stroj, a zvýšíme frekvenci kmitů. Když jich bude třeba tisíc za sekundu, tak mačkat tlačítko v tak přesných intervalech, aby to vždycky vyšlo ve stejné chvíli, zvládne jen Chuck Norris. Pro nás ostatní to bude stačit.

Použijeme tedy zapojení blikače, které lehce upravíme tak, aby blikalo rychleji. Máme tři možnosti:

1. Zmenšit kapacitu kondenzátoru.

2. Zmenšit odpor rezistoru.

3. Udělat obojí.

V kapitole o astabilních klopných obvodech jsem ukazoval vzorec f = 1 / (2,2RC). Pokud tedy chci blikání okolo 1 kHz, musí platit, že 1 / (2,2RC) = 1000, tedy 2,2RC = 0,001, tedy RC = 0,00045.

### 19.1.1 Jaké hodnoty RC zvolit, když vím jen to, že součin má být XYZ? {#19-1-1-jak-hodnoty-rc-zvolit-kdy-v-m-jen-to-e-sou-in-m-b-t-xyz}

_To je dobrá otázka. Něco podobného vyprávěl Feynman ve své knize vzpomínek, když líčil, jak kombinoval ozubená kola, aby dostal určitý poměr. Starší zkušený technik mu dal radu: „Vezmi katalog ozubených kol, vynech kola s příliš velkým počtem zubů a s příliš malým počtem zubů, a z těch středních hodnot to nějak nakombinuj!“_

_Dělejte to úplně stejně. Vyhněte se hodnotám příliš nízkým i příliš vysokým, a pokud to jde, použijte „zlatý střed“. A vždy začněte tím, co máte doma. Já bych sáhnul po kondenzátoru 100 nF, protože těch mám doma dost, a hlavně proto, že mám výrazně méně hodnot kondenzátorů (vlastně jen 100n, 33p a pak elektrolyty) než rezistorů (těch mám asi 30 základních hodnot)._

Jak to vychází pro 100 nF?

R = 0,00045 / 0,0000001 = 4500\. Tedy odpor 4k5\. Ten nemám, sáhnu tedy po odporu 4k7\. Bude to nějak moc vadit?

f = 1 / (2,2 × 4700 × 0,0000001) = 967 Hz (zhruba).

Což je hodnota přijatelná, v toleranci – ono je jedno, jestli to bude 1 kHz, nebo 0,967 kHz, důležité je, že to je „dost rychle na to, aby člověk nedokázal vychytat frekvenci“.

Kdybych neměl 4k7, dám tam 3k3, výsledná frekvence bude f = 1 / (2,2 × 3300 × 0,0000001) = 1377 Hz, tedy necelých 1,4 kHz.

Dobrá. Tohle všechno je OK, ale co kdybych chtěl tu frekvenci fakt přesnější? Měl bych hledat přesné rezistory a kondenzátory? Mohl bych, ale byla by to marná práce, protože oscilátor, založený na kondenzátoru a rezistoru, se bude velmi pravděpodobně rozlaďovat. Jistější by bylo použít obvod 555, který má díky teplotním kompenzacím přesnější chod, a úplně nejpřesnější by bylo vzít krystalový oscilátor. S největší pravděpodobností byste frekvenci 1,000 kHz nesehnali, tak by nezbývalo, než použít frekvenci vyšší a pak ji podělit.

[eknh.cz/pnor](https://eknh.cz/pnor)