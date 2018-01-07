## 20.1 Čítač s nulováním {#20-1-ta-s-nulov-n-m}

Pokud u klopných obvodů vyvedete vstup /CLR (tedy nulovací), získáte možnost kdykoli celý čítač „vynulovat“ a počítat opět 0 – 1 – 2 – 3…

![244-1.png](images/000072.png)

Co kdybychom u našeho čítače zapojili nulovací vstup tak, že se nastaví ve chvíli, kdy vývody B a C budou 1? Prostě přes hradlo AND – respektive NAND, protože vstup /CLR je aktivní v 0:

![244-2.png](images/000086.png)

Co se stane? Čítač bude postupně na vývodech CBA procházet stavy 000, 001, 010, 011, 100, 101, a pak vstoupí do stavu 110\. V tu chvíli se na vývodu hradla NAND objeví log. 0 (B NAND C), a tím se uvede do stavu 000\. Takovému zapojení se říká čítač se zkráceným cyklem – v tomto případě jsme zkrátili cyklus na šest kroků, 000 až 101, tedy desítkově 0 až 5.

Technicky samozřejmě platí, že se na vývodech objeví i stav 110, ale ten je tam jen velmi krátkou dobu, která odpovídá rychlosti hradla NAND a nulovacího vstupu. U běžných zapojení můžete takový stav ignorovat a zanedbat.

Máme tedy čítač, který čítá od 0 do 5\. Stejným způsobem můžete zkrátit čtyřbitový čítač tak, aby počítal 0 – 9:

![245-1.png](images/000101.png)

Výborně, máte tím pádem pořešené dělení desíti a dělení šesti. Když zapojíte za sebe děličku 10 a děličku 6, získáte děličku 60… Představte si teď, že na vstup zapojíte ten zmiňovaný hodinový signál s frekvencí 1 Hz. Co získáme? Ano, z prvního děliče budou jednotky sekund (0-9), z druhého desítky (0-5). Po hodnotě 59 bude následovat 00…

[eknh.cz/hod](https://eknh.cz/hod)