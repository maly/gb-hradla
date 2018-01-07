## 13.9 Pull Up a Pull Down {#13-9-pull-up-a-pull-down}

Fajn, už víte, jaké možnosti máte. A teď tedy zpátky k našemu problému, totiž vyřešit nějak nastavování jedniček a nul: co zapojit? A jak?

Klasické přepínače a spínače by šly použít, ale museli byste si k nim připájet vývody, co jdou zapojit do nepájivého kontaktního pole (NKP).

Můžete použít tahový přepínač, který jde sice do kontaktního pole zasunout, ale nedrží tam moc dobře, protože mívají krátké nožičky. Ale šlo by to: Na vstup hradla připojíte prostřední vývod (C), jeden krajní zapojíte na zem, druhý na Vcc, a bude to. Podle toho, jak přepnete, bude vývod C přepínače spojen buď se zemí, nebo s napájením, a bude na něm tedy buď log. 0, nebo log. 1\. A když budete přepínat rychle, tak minimalizujete i okamžiky, kdy na vstupu nebude ani zem, ani napájecí napětí, což je pro nás _zakázaný stav_.

![147-1.png](images/000296.png)

Nebo můžete použít mikrotlačítko, které do NKP sedne docela dobře, jenže neumí přepnout mezi dvěma póly. (Jsou taková tlačítka, spíš „přepínače s pružinou“, která se vždy vrací do výchozí polohy, ale ty teď neuvažujme.) Jak to uděláte?

Tak, v první řadě – zapojíte tlačítko mezi vstup hradla a napájecí napětí. Pokud bude tlačítko stisknuté, propojí vstup s Vcc a na vstupu bude tedy logická 1\. Pokud bude tlačítko rozpojené, tak… Co? No, v takovém případě nebude na vstupu nic konkrétního. Záleží na technologii obvodu, jak si s takovým stavem poradí, ale upřímně říkám, že třeba u obvodů CMOS stačí přiblížit ruku a stav se změní (vzpomeňte si na pokus s tranzistorem JFET)… Takže by bylo fajn tam mít po zbytek času zem.

A jestli mi nevěříte, zkuste si to sami. Použijte třeba 74HC00 (tady je to HC důležité, s obvodem LS, ALS apod. to fungovat nebude), zapojte LED na výstup hradla, jeden vstup připojte na + 5 V, druhý nechte nezapojený a podívejte se co se stane, když budete kolem toho nezapojeného šátrat prstem. Když k nezapojenému vstupu připojíte jeden konec vodiče a druhý necháte bimbat prostorem, stvoříte navíc anténu, citlivou i na statickou elektřinu, a nebudete se stačit divit, jak se bude LED chovat. Tedy až do té chvíle, kdy se zapomenete, poškrábete se zamyšleně na triku, tím si vytvoříte větší statický náboj, a když pak ruku přiblížíte k téhle anténě, tak se ozve suché zapraskání, které vám zároveň oznámí, že jste pravděpodobně právě zničili celý integrovaný obvod.

![148-1.png](images/000121.png)

Říkáte si _dobře, tak to propojím se zemí, aby byl klid a žádné rušení?_ To není moc dobrý nápad. Co by se stalo? Dokud není tlačítko stisknuté, tak je vstup propojen se zemí a je na něm log. 0\. Jakmile tlačítko zmáčknete, tak se propojí napájecí napětí se zemí, vytvoří se zkrat, kterým poteče tolik proudu, kolik jen zdroj dokáže dát a kolik vodiče snesou, ostatní obvody zůstanou bez proudu (většina poteče zkratem) a je zle. Takhle tedy ne!

Dělá se to tedy tak, že mezi vstup a zemi zapojíte rezistor, třeba 10k. Pokud je tlačítko rozpojené, tak je vstup obvodu skrz něj připojen k zemi, a je tam tedy nula. Když stisknete tlačítko, tak sice vznikne zkrat, kterým poteče I = U / R = 5 / 10000 = 0,5 mA, ale zároveň dostanete na vstup požadovaných (skoro) 5 V.

![149-1.png](images/000238.png)

[eknh.cz/7400](https://eknh.cz/7400)

Této technice se říká pull-down rezistor – jako že „táhne vstup dolů, k zemi, k nule“. Když to zapojíte obráceně, tedy tlačítko na zem a rezistor na napájecí napětí, stvoříte pull-up, tedy zapojení, kde rezistor „táhne vstup nahoru“ – myšleno k logické 1\. Tento model je velmi častý a setkáte se s ním u spousty zapojení. Ovšem funkce tlačítka pak bude obrácená: při stisknutí spojí vývod na log. 0, při puštění log. 1.