## 14.8 Multiplexor {#14-8-multiplexor}

V anglické literatuře se tentýž obvod jmenuje multiplexer, a česky jsem slyšel oba tvary. Ačkoli se většinou přimlouvám za jednotnou terminologii, tak zrovna u tohoto slova používám oba tvary. Hanba mi!

Multiplexor je „digitálně řízený přepínač“. V základní podobě má několik signálových vstupů (třeba 2, označme si je A a B), jeden výstup (Q) a jeden řídicí vstup (S), který říká, který ze vstupů má být připojen na výstup. U našeho dvouvstupového multiplexoru stačí jeden řídicí bit. Funkce je pak v závislosti na hodnotě S následující:

| S | Y |
| --- | --- |
| 0 | hodnota ze vstupu A |
| 1 | hodnota ze vstupu B |

Jasné? Pokud ne, tak si to celé ještě rozepíšeme:

| S | A | B | Y |
| --- | --- | --- | --- |
| 0 | 0 | 0 | 0 |
| 0 | 0 | 1 | 0 |
| 0 | 1 | 0 | 1 |
| 0 | 1 | 1 | 1 |
| 1 | 0 | 0 | 0 |
| 1 | 0 | 1 | 1 |
| 1 | 1 | 0 | 0 |
| 1 | 1 | 1 | 1 |

Všimněte si, že funkce odpovídá slovnímu popisu výše: pokud je S = 0, je na výstupu Y hodnota, která je na vstupu A, a vstup B se ignoruje. Pokud je S = 1, je na výstupu hodnota ze vstupu B bez ohledu na vstup A.

Můžeme navrhnout různá zapojení, ale nejjednodušší získáme, když si uvědomíme to, co jsme si řekli výše o hradlech: vstup S bude povolovat buď signál A, nebo signál B. Signál B bude povolovat, pokud bude roven 1\. Takže „povolený signál B“ bude vlastně „B AND S“. Signál A je povolen v nule, takže „povolený signál A“ bude „A AND NOT S“. No a protože víme, že „zakázaný signál“ je 0, a nula je zároveň neutrální hodnota pro OR, můžeme výsledek zapsat jako „povolené A OR povolené B“ – po dosazení tedy „(A AND NOT S) OR (B AND S)“.

A jak řekli, tak udělali…

![167-1.png](images/000315.png)

[eknh.cz/muxao](https://eknh.cz/muxao)

Náš multiplexor byste tedy mohli poskládat z jednoho obvodu OR (7432), z jednoho invertoru (7404) a ze dvou hradel AND (7408). Jenže: z OR byste využili jednu čtvrtinu obvodu 7432 (1 hradlo ze čtyř), z invertorů jednu šestinu a z AND pouhou polovinu obvodu (2 hradla ze čtyř). A to se nevyplatí.

Naštěstí to dělat nemusíte, protože většinu složitějších obvodů už za nás někdo poskládal a udělal je jako samostatné součástky. I multiplexory a další. Ale teď neřešme, jestli _to už existuje_, ale přemýšlejme, _jak to udělat_? Protože cílem této knihy je i to, abyste uměli vymyslet vlastní složitější konstrukci z jednodušších komponent.

Pomocí hradla AND-OR jsme stvořili multiplexor. Tedy teoreticky, nijak jsme si ho nezapojovali – nanejvýš v emulátoru. Jeho funkce spočívá v propojení vybraného vstupu s výstupem. Vstup se vybírá pomocí řídicího vstupu S. V naší nejjednodušší podobě má řídicí vstup S jeden bit, proto může vybrat jeden ze dvou vstupů. Pokud použijeme dva řídicí bity S1 a S2, můžeme vybrat jeden ze čtyř vstupů. Při třech řídicích bitech jeden z osmi vstupů. V praxi jsou nejčastěji používány právě tyto tři multiplexory, totiž se dvěma, čtyřmi a osmi vstupy.

Zkusme si cvičně vytvořit soustavu rovnic pro čtyřvstupový multiplexor:

Y = (A AND NOT S1 AND NOT S2) OR

  (B AND S1 AND NOT S2) OR

  (C AND NOT S1 AND S2) OR

  (D AND S1 AND S2)

Na každém řádku je zapsaný logický součin pro jeden vstup. NOT S1 AND NOT S2 je splněno pro S1 = S2 = 0, S1 AND NOT S2 je splněno pro S1 = 1, S2 = 0 a tak dále. Takto vlastně „hradlujeme“ čtyři vstupy, a nakonec je prostě sloučíme do jednoho.