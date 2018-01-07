## 32.4 Složitější periferie {#32-4-slo-it-j-periferie}

V našem příkladu jsme použili jednoduchý obvod a stvořili jsme tak primitivní paralelní výstup. Na ten bychom mohli připojit, dejme tomu, nějaké řízení, nebo sedmisegmentovku, nebo něco takového.

Podobným způsobem, ale pomocí obvodu s třístavovými výstupy, bychom mohli udělat vstupní periferii (například s obvodem 74HCT244). A opravdu se tak dělaly. Ovšem bylo to velmi náročné na obvody i na konstruktéra.

Postupem času přišly složitější periferie, většinou programovatelné. Příkladem mohou být dva obvody, 8255 a 8251.

Obvod 8255 obsahuje tři obousměrné paralelní osmibitové porty PA, PB a PC, proto se označuje jako PIO – Parallel Input and Output. K procesoru se připojuje přes datovou sběrnici a dva adresové vstupy. Dále obsahuje vstup RESET a vstup /CS – známý Chip Select, který připojuje tento obvod ke sběrnici.

Ta nejzajímavější vlastnost obvodu 8255 je, že je konfigurovatelný. Podle kombinace na vstupech A0 a A1 procesor komunikuje buď s registry jednotlivých portů PA, PB, PC, nebo zapisuje a čte do/z osmibitového řídicího registru CWR. Pomocí zápisu do tohoto registru lze jednak ovládat přímo jednotlivé bity portu PC, ale také nastavit mód práce. Obvod totiž může fungovat jako tři nezávislé datové porty, ale také může rozdělit porty do dvou skupin (PA + polovina PC, PB + druhá polovina PC) a rozdělené signály portu PC využívat jako řídicí signály pro přenos dat, např. pro oznámení, že data byla přijata nebo naopak že je požadováno jejich převzetí apod.

Obvod 8251 se používal v osmibitových počítačích spolu s obvodem 8255\. Zatímco 8255 nabízí paralelní rozhraní, 8251 nabízí sériové rozhraní. V kapitole o rozhraních jsme si říkali, že se pro rozhraní RS-232 používaly obvody UART/USART – no a 8251 je právě USART, neboli Univerzální Synchronní / Asynchronní Přijímač a Vysílač (rozuměj: sériových dat).

![360-1.png](images/000279.png)

S procesorem komunikuje tento obvod opět přes datovou sběrnici a pomocí řídicích signálů /RD, /WR. Obvod se připojuje na sběrnici ve chvíli, kdy je aktivní vstup /CE. Vstup C/D určoval, jestli se zapisují nebo čtou data (=0), nebo řídicí / stavové informace (=1). V praxi se připojoval k některému z adresních signálů, např. k A0\. Pokud byl obvod adresován například tak, že byl aktivní na adrese 0x20, a vstup C/D byl zapojen na A0, tak se adresou 0x20 přistupovalo do datového registru, adresou 0x21 do řídicího.

Ve schématu jsou vidět i všechny signály, o nichž jsme mluvili v kapitole o sériové komunikaci. Všechny ty DSR, DTR, CTS, RTS a podobné, které řídí, kdy se může vysílat a kdy ne. Vlastní datový přenos probíhal po linkách TxD, RxD – u synchronního přenosu se používaly i hodiny TxC, RxC.

Dalšími používanými periferiemi byly například čítače a časovače 8253 (nebo Z80-CTC). Tyto obvody obsahují programovatelné čítače, které dokázaly počítat nějaké vnější události, např. hodinové impulsy, a při splnění určité podmínky buď změnily signál na výstupu, nebo např. vyvolaly přerušení.

Mezi periferie se počítaly i zobrazovací jednotky. Některé displeje fungovaly naprosto transparentně, tj. zobrazovaly data, která byla někde v paměti, bez účasti procesoru, jiné bylo potřeba předem přepnout, nastavit do nějakého vhodného pracovního módu – tak fungovaly například videořadiče od Motoroly MC6845 (používané i v grafických kartách MDA a Hercules u IBM PC), nebo např. TMS9918 (výrobce Texas Instruments).

Další periferie, například vnější paměti apod., většinou nemívaly vlastní obvod a připojovaly se přes standardní rozhraní. Výjimkou byly floppy disky (diskety), které měly vlastní řadiče – známé typy Intel 8272, WD2797 nebo WD1793, které se používaly např. v disketových jednotkách, vyráběných pro počítač ZX Spectrum…