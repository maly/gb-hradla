## 34.1 Šetříme vývody {#34-1-et-me-v-vody}

Maticové uspořádání je fajn, především díky tomu, že maticově uspořádaná tlačítka můžeme snadno číst přímo jednočipem, bez dalších obvodů.

Pokud ale chceme ušetřit ještě nějaké vývody, nezbude než sáhnout po podpůrných obvodech. Třeba náš oblíbený 74LS138, neboli dekodér 1-z-8\. Našich zmiňovaných 16 tlačítek bychom mohli zapojit do matice 2 × 8, řádek by se vybíral binární kombinací na vstupech A0-A2, a četly by se dva sloupce. Dohromady pět vodičů. V případě klávesnice ZX Spectra (5 × 8) by nám stačilo 8 vodičů celkem (3 pro výběr řádku, 5 pro čtení sloupce).

Můžeme ušetřit ještě víc – existovaly obvody, zvané _prioritní enkodér_, které dokázaly obsluhovat celé pole tlačítek a na výstupu přímo oznamovaly kód, jaké tlačítko bylo stisknuto. Nevýhodou bylo, že tyto obvody byly drahé, málo dostupné a neřešily situaci, kdy uživatel stisknul několik tlačítek naráz (Ctrl Alt Del by asi neprošlo).

Když se podíváte na klávesnici PC, vidíte přes sto tlačítek, a přitom jen několik vodičů. Je to jednoduché: v klávesnici je speciální obvod, který neustále kontroluje matici tlačítek a po sériové lince posílá informaci o změnách – které tlačítko bylo stisknuto, které puštěno. V prvních PC klávesnicích byl v této roli použit jednočip 8048...