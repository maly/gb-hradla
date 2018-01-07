## 32.2 Přerušení {#32-2-p-eru-en}

Přerušení je velmi podstatný koncept v procesorovém světě. Jde o způsob, jakým dává okolí vědět procesoru, že se stalo něco, na co je třeba bezprostředně zareagovat. Může to být například informace o tom, že na klávesnici někdo stiskl klávesu, může to být signál, že přišla data po sériové lince, nebo může jít o pravidelný hodinový signál. Může jít o naprogramovaný signál typu „za 10 milisekund“, nebo může jít třeba o výše zmíněný signál od obvodu DMA.

U procesoru 8080 slouží k vyvolání přerušení vstup INT. Na konci každé instrukce procesor testuje stav tohoto vstupu. Pokud je aktivní, pozná, že jde o přerušení. Pokud není přerušení zakázáno (což může programátor zařídit speciální instrukcí), udělá to, že přečte jednu instrukci z datové sběrnice, zakáže další přerušení a instrukci vykoná.

Tou jednou instrukcí bývala instrukce RST0 až RST7 – speciální obvod se staral o to, aby různé požadavky na přerušení měly různé instrukce. Instrukce RST jsou vlastně zkrácené instrukce volání podprogramu na adresách 0, 0x8, 0x10, 0x18, … 0x38.

Pro jednoduché systémy šlo zařídit, aby vždy přerušení vyvolalo instrukci RST7, tedy volání podprogramu na adrese 0x0038\. Po příchodu požadavku na přerušení tedy procesor skočil do podprogramu na adrese 0x0038, tam musel programátor požadavek vhodně obsloužit, pak opět přerušení povolit a vrátit se zpět do hlavního programu.

### 32.2.1 Nemaskovatelné přerušení {#32-2-1-nemaskovateln-p-eru-en}

Jiné procesory, třeba známý Z80, mají dva různé typy přerušení – maskovatelné a nemaskovatelné. Maskovatelné přerušení odpovídá tomu, co známe z procesoru 8080 (v procesoru Z80 máme k dispozici dokonce tři módy, což teď není podstatné).

Maskovatelné přerušení může programátor zakázat – „zamaskovat“ – pomocí speciální instrukce DI (Disable Interrupt). Tato instrukce nastaví vnitřní příznak v procesoru (technicky: zase jeden klopný obvod). Vstup /IRQ (Interrupt Request) je tímto příznakem „maskován“ – pokud je přerušení zakázáno, signál se nedostane dál a požadavek je ignorován. „Odmaskovat“ přerušení lze instrukcí EI (Enable Interrupt).

Kromě maskovatelného přerušení /IRQ existuje i signál nemaskovaného přerušení /NMI (Non Maskable interrupt). Tento signál vždy vyvolá přerušení, bez ohledu na instrukce DI/EI.