## 18.11 Reálný klopný obvod D: 7474 {#18-11-re-ln-klopn-obvod-d-7474}

Samozřejmě že máme k dispozici popsaný klopný obvod typu D jako součástku. A ano, dodneška se používá. Nejznámější obvod je 7474 (a my už víme, že to může být i 74LS74, nebo 74HCT74). Tento obvod obsahuje dvojici klopných obvodů typu D. Jeho datasheet naleznete třeba zde: [sn74ls74a](http://www.ti.com/lit/ds/symlink/sn74s74.pdf). V popisu je napsáno, že jde o „Dual D-type Positive-Edge-Triggered Flip-Flops with Preset and Clear“. Pojďme si to v rámci cvičení přeložit.

• „Dual“ naznačuje, že v jednom pouzdru jsou dva klopné obvody stejného typu. Česky „dvojitý“.

• „D-type Flip-Flop“ říká, že jde o klopný obvod (flip-flop – vážně, takhle se v anglické literatuře říká klopným obvodům) typu D.

• „Positive edge triggered“ si rozluštíme jako „spouštěný náběžnou hranou“. Trigger je spoušť, tady to symbolizuje onu akci, která se provede – třeba „zapamatování údajů“. Positive edge je takzvaná „náběžná hrana“. Když se podíváte na vizualizaci hodinového pulsu, tak ta svislá čára vlevo, jak stoupá zespoda nahoru, tomu se říká „náběžná“ (též „vzestupná“) hrana hodinového pulsu. Ta druhá, přechod shora dolů, je sestupná hrana, anglicky pak „negative edge“. Někdy se setkáte i s termíny „falling edge“ (sestupná) a „lead edge“ (náběžná).

• „with preset and clear“ říká, že jde o klopný obvod D, který má nastavovací a nulovací vstup. Někdy se dodává, aby to bylo jasnější, i slovo „asynchronous preset and clear“. Jde v podstatě o naše vstupy R a S, jen s tím rozdílem, že jsou připojeny přímo do klopného obvodu a nečekají až na hodinový impuls.

Schematická značka to celé hezky ilustruje:

![226-1.png](images/000198.png)

Vidíte dva vstupy D a C (ten má funkci hodin), vstupy PRE a CLR (negované) a dva výstupy, Q a /Q.

Všimněte si: u podobných obvodů se nekreslí napájení. Samozřejmě, že obvod musí být připojený na napájecí napětí, ale to se bere samo sebou, automaticky, takže ho není nutné kreslit.

Schéma vnitřního zapojení je ve skutečnosti o něco složitější než je výše uvedený „latch“ – to proto, aby obvod reagoval opravdu jen na přepnutí z 0 do 1, a ne na jiné události:

![227-1.jpeg](images/00217.jpeg)

Naštěstí se zapojením nemusíte zabývat. Vám stačí znát funkční tabulku:

| Vstupy | Výstupy |
| --- | --- |
| /PRE | /CLR | CLK | D | Q | /Q |
| 0 | 1 | X | X | 1 | 0 |
| 1 | 0 | X | X | 0 | 1 |
| 0 | 0 | X | X | 1* | 1* |
| 1 | 1 | ^ | 1 | 1 | 0 |
| 1 | 1 | ^ | 0 | 0 | 1 |
| 1 | 1 | 0 | X | Q0 | /Q0 |

Nerozumíte? Vysvětlení je zde:

Vstupy /PRE a /CLR jsou zmiňované „preset“ (=„nastav na 1“) a „nuluj“ (=„nastav na 0“). Lomítko před názvem znamená, jak už jsme si řekli, negaci, takže klidový stav je 1, a požadovanou akci spustíme hodnotou 0.

Zatím jsme se setkávali s pozitivními signály, tedy takovými, kdy 0 znamenala „klid“ a 1 nějakou akci. U negovaných vstupů to je obráceně. Některé signály se v číslicové technice používají právě v takovéto negované podobě. Má to své důvody, o nichž jsme se už bavili, tak jen připomenu: logická 1 má širší rozsah napětí, tak je odolnější proti rušení.

První řádek ukazuje stav, kdy je aktivní signál PRESET (na vstup /PRE je přivedena logická 0, na vstupu /CLR je logická 1, tedy „klid“). Vstupy CLK a D mohou být v libovolné úrovni, což značíme symbolem X. V takovém případě se obvod „nastaví“, na výstupu bude 1, na negovaném výstupu bude tedy 0.

Druhý řádek. Je aktivní signál CLEAR (tedy /CLR je 0, /PRE je 1, CLK a D libovolné). Situace je analogická předchozí, ale obráceně: obvod se „vynuluje“, na výstupu bude 0, na negovaném výstupu 1.

Třetí řádek označuje hazardní stav. Oba asynchronní vstupy PRE i CLR jsou aktivní (tedy v úrovni 0), oba výstupy jsou v logické 1, a v datasheetu je ještě u toho poznámka, že nelze zaručit správnou úroveň napětí na výstupu, takže do takového stavu by se neměl obvod dostávat.

Poslední tři řádky popisují situaci, kdy jsou asynchronní vstupy v klidu (=log. 1). V takové situaci obvod funguje tak, jak jsme si popsali výše. Pokud je CLK rovno 0, tak bez ohledu na stav vstupu D je na výstupech to, co tam bylo předtím (poslední řádek tabulky). Změna probíhá s náběžnou hranou signálu CLK (symbolizováno stříškou ^) – pokud je D = 1, bude i Q = 1 (a /Q logicky 0), pokud je D = 0, bude Q = 0 (a /Q = 1).

Reálná součástka je v pouzdře DIL se 14 vývody, které jsou zapojeny takto:

![229-1.png](images/000046.png)

A protože jsou uvnitř dva nezávislé klopné obvody, jsou i všechny vstupy a výstupy v obvodu dvakrát. Při pohledu shora vidíte vlevo vývody obvodu 1 postupně pod sebou: /CLR, D, CLK, /PRE, Q a /Q. Vpravo je totéž pro obvod 2.

Možná vás mate, že hodiny se tu značí CLK, zatímco já vám výš tvrdil, že se značí C. Víte, ve skutečnosti je to jedno – CLK nebo C, obojí je přijatelné, když je jasné, o čem je řeč. Někdy se setkáte i s označením CK a někdy ještě jinak, ale vždy je někde napsáno, že se jedná o hodinový vstup (clock).