## 18.5 Detektor pohybu {#18-5-detektor-pohybu}

Jdeme stavět. Chcete? Já vím, že ano. Postavíme si něco s čidlem PIR.

PIR jsou pasivní infračervená čidla (proto ta zkratka: Passive Infra-Red), která zachycují pohyb objektů o specifické teplotě. Člověk mívá povrchovou teplotu těla někde mezi 35-37 °C, a jak známo: každý teplý objekt vysílá infračervené záření určité vlnové délky, která je nepřímo úměrná teplotě objektu.

Čidlo PIR má čip, citlivý na infračervené záření, před ním filtr, který odfiltruje (alespoň nějaké) cizí zdroje tepla, a okolo je takzvaná Fresnelova čočka, která koncentruje záření z okolí do jednoho bodu. Zároveň dává PIR čidlu charakteristický vzhled:

![217-1.jpeg](images/00094.jpeg)

Takovéto moduly jsou dobře dostupné a velmi jednoduché na zapojení. Mají jen tři vývody – zem, napájení (+ 5 voltů) a výstup informace o tom, že se něco děje (Output). Zapojte si nějaké testovací zapojení, třeba takto:

![217-2.png](images/000399.png)

A můžete testovat chování. LED normálně nesvítí. Jakmile před čidlem mávnete rukou, nebo se výrazněji pohnete, LED se rozsvítí asi na 1 sekundu. To je celé. Jednoduché, že?

Znáte takové ty automaty, co rozsvítí světlo na chodbě, když se někdo pohne? Zvládnete ho postavit? Já věřím, že ano… Schválně, napadá vás vhodný způsob?

Bude tam PIR, to je jasné. PIR dá při pohybu na výstupu krátký puls. Ten nestačí, to bychom udělali krok a světlo by zhaslo. Je potřeba z krátkého pulsu udělat delší…

Stačí monostabilní klopný obvod. Takový, jako jsme udělali na konci předchozí kapitoly, spínaný do logické 1\. Jen ten čas by měl být delší…

Zkusme tedy dát co největší kapacitu a co největší odpor. Mně se v šuplíku válel kondenzátor 47 μF. K němu jsem našel rezistor 1M5, tedy 1,5 MΩ. Když si doplníte hodnoty do výše uvedeného vztahu, zjistíte, že čas sepnutí bude zhruba jedna minuta. A to je přijatelné.

Co dál? PIR čidlo zajistí detekci pohybu, monostabilní KO prodlouží tento impuls na minutu, a ještě nějak musíme zařídit to slíbené světlo. Pokud stačí jedna LED, není co řešit, připojte ji na výstup MKO. Ovšem případů, kdy na osvětlení chodby stačí jedna LED není zas tolik (krom domečků pro panenky), takže bude potřeba sepnout větší světelný zdroj.

Už jsem to tu psal tolikrát, že to bude možná vypadat, že mám sklerózu a zapomínám, co jsem už napsal, popřípadě že trpím neschopností myšlenku opustit, ale zopakuju to znovu: Velký světelný zdroj = velký proud. Výstup invertoru = malý proud. Musíte použít něco, co z malého proudu udělá velký. Pokud budete rozsvěcovat světlo, napájené třeba pěti volty, použijte tranzistor. Pokud budete spínat třeba 230 V žárovku (na střídavý proud), použijte relé (a tranzistor k jeho sepnutí).

A na tomto místě vám velmi silně doporučím nepoužívat 230 V žárovku! Vážně! Nebo jinak: Zakazuju vám připojovat cokoli se síťovým napětím do konstrukcí, co stavíte! Ne že by to nešlo, jde to, teoretickou výbavu máte, ale síťové napětí, nezlobte se, tam jde o zdraví, bezpečnost a o lidské životy (bez nadsázky). Nedělejte to, a alespoň ze začátku si k tomu vždy přizvěte někoho zkušeného, znalého techniky a oprávněného takové věci dělat!

Vážně. Děkuju.