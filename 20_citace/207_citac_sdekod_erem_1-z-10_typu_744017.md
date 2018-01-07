## 20.7 Čítač s dekodérem 1-z-10 typu 744017 {#20-7-ta-s-dekod-rem-1-z-10-typu-744017}

Už jsem tu zmínil, že kromě TTL řady 74xx existovala i řada CMOS 40xx, v níž bylo několik velmi zajímavých obvodů. Protože konstruktéři tyto obvody používali a museli řešit přizpůsobení úrovní mezi CMOS a TTL, sáhli výrobci k řešení: vyrobili funkčně a vývodově shodné obvody.

Příkladem takového obvodu může být 4075, což je trojice třívstupových hradel OR, a její TTL ekvivalent 744075 (74HCT4075). Zajímavý obvod je 4017, v TTL verzi jako 744017 – např. 74HCT4017\. Tento obvod kombinuje pětibitový Johnsonův čítač (tedy s deseti hodnotami) a dekodér 1-z-10, takže má deset výstupů, pro každou hodnotu jeden. Což se může hodit v nejrůznějších situacích.

![264-1.png](images/000331.png)

Obvod má nulovací vstup R, hodinový vstup CLK a povolovací vstup /CE – pokud je neaktivní (=1), čítač ignoruje vstup CLK, pokud je aktivní (=0), vstup CLK funguje. Z výstupů Q0 až Q9 je aktivní právě jeden, podle aktuálního stavu. Negovaný výstup /CO (Carry Out) je neaktivní (=1) pro hodnoty 0 až 4, pro hodnoty 5-9 je aktivní (=0).

U tohoto čítače můžeme zkrátit periodu velmi snadno – chceme-li například omezit hodnoty na 0-5, propojíme výstup Q6 s resetovacím vstupem.

Pokud jej použijeme pro naši hrací kostku, nebudeme potřebovat další integrovaný obvod, namísto toho použijeme pouze montážní OR, protože:

D = Q0 or Q2 or Q4

AG = Q1 or Q2 or Q3 or Q4 or Q5

BF = Q5

CE = Q3 or Q4 or Q5