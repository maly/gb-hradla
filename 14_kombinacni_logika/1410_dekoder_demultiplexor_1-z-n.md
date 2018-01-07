## 14.10 Dekodér (demultiplexor) „1-z-N“ {#14-10-dekod-r-demultiplexor-1-z-n}

Demultiplexor je součástka s opačnou funkcí, než má multiplexor. Má jeden signálový vstup, několik výstupů, a řídicí vstup, který říká, na jaký výstup bude vstup připojen. Ostatní výstupy budou v logické nule, případně ve třetím stavu (za chvíli si o něm něco povíme).

Speciálním případem demultiplexoru je dekodér – ten nemá signálový vstup, jen výstupy a řídicí vstupy. Podle toho, jaká kombinace je na řídicích vstupech, je na zvoleném výstupu jednička, na ostatních nula (nebo obráceně).

Dekodéry se používají nejčastěji 1-ze-4, 1-z-8, 1-z-10 a 1-z-16\. Mají tedy dva, tři nebo čtyři řídicí vstupy a odpovídající počet výstupů. Logická funkce je podobná té u multiplexoru:

Y1 = NOT S1 AND NOT S2

Y2 = S1 AND NOT S2

Y3 = NOT S1 AND S2

Y4 = S1 AND S2

| S1 | S2 | Y1 | Y2 | Y3 | Y4 |
| --- | --- | --- | --- | --- | --- |
| 0 | 0 | 1 | 0 | 0 | 0 |
| 0 | 1 | 0 | 1 | 0 | 0 |
| 1 | 0 | 0 | 0 | 1 | 0 |
| 1 | 1 | 0 | 0 | 0 | 1 |