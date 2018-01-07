## 35.1 Multiplexior / Demultiplexor {#35-1-multiplexior-demultiplexor}

Pamatujete na kapitolu o číslicové technice? Multiplexor vybírá jeden z mnoha vstupů, a ten posílá na výstup, demultiplexor (dekodér) zase aktivuje jeden z několika výstupů.

Představme si tedy matici 8 × 8 tlačítek. Buzení řádků zařídí náš oblíbený 74LS138 – stručně zopakuju: obvod má tříbitový vstup a osm výstupů, které jsou v log. 1 kromě toho, jehož číslo odpovídá tříbitovému číslu na vstupech.

Osm sloupců bude zase připojeno na multiplexor, třeba 74HCT151\. Tento obvod má pro změnu osm datových vstupů, tři vstupy adresy a dva výstupy, Y a /Y. Na výstup je připojen ten vstup, jehož číslo… a tak dál…

Takže potřebujete tři vývody na výběr řádku, tři vývody na výběr sloupce, a jeden vstup, který řekne, jestli dané tlačítko je nebo není stisknuté. 64 tlačítek tak obsloužíte pomocí 3 + 3 + 1 = 7 signálů. Na poloviční počet tlačítek stačí 6 vodičů…

A co na to jít ještě jinak?