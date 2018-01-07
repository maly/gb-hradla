## 14.3 Logické funkce dvou proměnných {#14-3-logick-funkce-dvou-prom-nn-ch}

Dvě vstupní proměnné mohou nabývat celkem čtyř kombinací: 00, 01, 10 a 11\. Každé téhle kombinaci odpovídá nějaká hodnota na výstupu, kterou můžeme zapsat jako čtyřbitové slovo – jako bychom četli poslední sloupec pravdivostní tabulky shora dolů.

Pro OR to je 0111, pro NOR 1000, pro AND 0001, pro NAND zase 1110...

Máme tedy 16 možných výsledků, od 0000 (vždy 0) po 1111 (vždy 1). Pojďme si je zase zapsat do tabulky.

| AB | Funkce | Poznámka |
| --- | --- | --- |
| 00 | 01 | 10 | 11 |
| 0 | 0 | 0 | 0 | Y = 0 | Kontradikce, vždy 0 |
| 0 | 0 | 0 | 1 | Y = A AND B | Součin (konjunkce) |
| 0 | 0 | 1 | 0 | Y = NOT (A –&gt; B) | Nonimplikace |
| 0 | 0 | 1 | 1 | Y = A | Projekce A |
| 0 | 1 | 0 | 0 | Y = NOT (A &lt;– B) | Obrácená nonimplikace |
| 0 | 1 | 0 | 1 | Y = B | Projekce B |
| 0 | 1 | 1 | 0 | Y = A XOR B | Nonekvivalence |
| 0 | 1 | 1 | 1 | Y = A OR B | Disjunkce |
| 1 | 0 | 0 | 0 | Y = NOT (A OR B) | NOR |
| 1 | 0 | 0 | 1 | Y = A XNOR B | Ekvivalence |
| 1 | 0 | 1 | 0 | Y = NOT B | Negace B |
| 1 | 0 | 1 | 1 | Y = A &lt;– B | Obrácená implikace |
| 1 | 1 | 0 | 0 | Y = NOT A | Negace A |
| 1 | 1 | 0 | 1 | Y = A –&gt; B | Implikace |
| 1 | 1 | 1 | 0 | Y = NOT (A AND B) | NAND |
| 1 | 1 | 1 | 1 | Y = 1 | Tautologie, vždy 1 |

Není jich víc? Co?

No, opravdu není. Tahle tabulka vyčerpala všechny možné kombinace výsledků pro všechny možné kombinace dvou vstupních hodnot.

Všimněte si, že v tabulce jsou naši staří známí (AND, NAND, OR, NOR, XOR a jeho negovaný bratr XNOR), jsou tam i funkce jedné proměnné (negace a projekce), jsou tam funkce, které jsou vždy 0, nebo vždy 1 (a přátelé, taková funkce, to snad ani není funkce!), a jsou tam ještě čtyři funkce implikace (normální, obrácená, a dvě jejich negované varianty). Funkce implikace jako jediné porušují pravidlo komutativnosti, tedy když zaměníme vývody A a B, dostaneme jinou funkci. Po pravdě řečeno nevím o tom, že by někdo „implikační“ hradla vyráběl jako integrovaný obvod. Pokud už někdo potřebuje třeba implikaci (1101), tak použije například hradlo OR, a na vstup A připojí invertor. Schválně se podívejte, jestli implikace není totéž co (NOT A) OR B.
