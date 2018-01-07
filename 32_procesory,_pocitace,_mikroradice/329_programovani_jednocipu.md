## 32.9 Programování jednočipů {#32-9-programov-n-jedno-ip}

Víme, že v jednočipu je paměť FLASH a v ní je uložený program. Víme, že některé konstrukce (Arduino třeba) a některé jednočipy mají k dispozici program, který umožní po startu zkontrolovat sériovou linku, jestli náhodou někdo nepožaduje zápis. (Podobný systém používaly například mikrokontroléry Dallas Semiconductors, které měly jádro 8051, a kromě standardní paměti měly i zabudovaný program „monitor“, který umožňoval jednoduchou práci po sériové lince.)

Pokud jednočip takovou možnost nemá, je potřeba jej naprogramovat jinak. Možná vás to překvapí, ale třeba u AVR i PIC se tak děje způsobem, který je velmi podobný zápisu do sériové FLASH po sběrnici SPI. Podrobnosti jsou uvedeny vždy v datasheetu, ale většinou je nějakým způsobem využit signál /RESET, který uvede čip do stavu, kdy naslouchá na sběrnici SPI a pokud přijdou správná data, započne programování.

Starší jednočipy potřebovaly, podobně jako paměti EPROM, vyšší napětí, typicky 12 voltů. Toto vysoké napětí se přivedlo na signál RESET a signalizovalo, že bude následovat programování.

Novější jednočipy od tohoto způsobu ustoupily. Důvod byl jednoduchý: díky tomu, že se nepřivádělo napětí 12 V, ale pouze 5 V, mohly čipy za určitých okolností zůstat zapojené v obvodu a být naprogramovány přímo na místě. Tomuto programování se někdy říká In-Place Programming nebo In-Circuit Serial Programming (ICSP / ISP).

Arduino lze dokonce přeprogramovat speciálním firmware tak, aby fungovalo jako programátor pro jednočipy AVR, a to právě v režimu ICSP.

Jiné jednočipy, především ty s jádrem ARM, mají takzvané „JTAG“ obvody. Toto rozhraní funguje podobně jako výše zmíněné ICSP. Navíc mívá toto rozhraní schopnost ovládat procesor za běhu, přerušit jeho práci, přečíst vnitřní stav registrů a zjistit stav na vstupech a výstupech, takže se používá i pro ladění programů.

Další výrobci navrhují další a další způsoby, jak programovat jednočipy a jak ladit programy. Tyto způsoby jsou většinou nekompatibilní, takže pokud budete používat více rodin jednočipů, budete mít zároveň i několik programovacích rozhraní a programátorů, většinou poměrně drahých.

##### 33 Displeje {#33-displeje}
