## 13.5 Booleova algebra, výroková logika {#13-5-booleova-algebra-v-rokov-logika}

Booleova algebra (kterou nám připomínají typy Boolean nebo Bool z některých programovacích jazyků) je širší pojem, který se v číslicové technice scvrkává na operace s _logickými hodnotami_. Logické hodnoty, též _pravdivostní_, jsou hodnoty logických _výroků_, které nabývají dvou různých stavů: _Pravda_ a _Nepravda_. Anglicky True a False. Typicky:

• Venku prší. Ano, nebo ne? Pravda, nebo nepravda?

• Mám deštník. Mám, nebo nemám? Pravda? Nepravda?

• Přines mi jídlo. Tohle není výrok, u kterého můžeme rozhodnout o jeho pravdivosti. Pardon, to jen na ukázku, že ne všechno je výrok.

• Přinesl jsi mi jídlo. Tady už rozhodnout lze. Přinesl? Nepřinesl? Ano, nebo ne?

Takovéto výroky jsou výroky _jednoduché_. Jazyk (a každodenní zkušenost“ nás učí, že takovéto jednoduché výroky můžeme spojovat do složitějších složených výroků pomocí spojek, jako je „a“ či „nebo“. _Venku prší a mám deštník._

Funkci spojek zastávají ve výrokové logice takzvané _logické operátory_. Představme si je podobně jako v matematice – třeba operátor sčítání, operátor násobení, … Můžeme je převést i do podoby _logické funkce_ a místo A AND B zapisovat AND (A, B).

Pojďme si dát příklad:

Čtyři sběratelé, Adam, Bořek, Cyril a David (a je jen náhoda, že si je můžu označit A, B, C a D), sbírají různé věci, a to takto:

• Adam sbírá známky a krabičky od zápalek.

• Bořek sbírá mince.

• Cyril sbírá známky i mince.

• David sbírá mince a krabičky od zápalek.

Ke každému pánovi můžeme vytvořit sadu výroků: „Sbírá mince“, „sbírá známky“, „sbírá krabičky od zápalek“, a o každém výroku můžeme říct, zda je pravdivý nebo ne. Tedy: „A sbírá mince“ je výrok nepravdivý, „A sbírá známky“ je výrok pravdivý, a tak dále. Zapíšeme si to do takzvané „pravdivostní tabulky“:

|  | Sbírá mince | Sbírá známky | Sbírá krabičky |
| --- | --- | --- | --- |
| Adam | ne | ano | ano |
| Bořek | ano | ne | ne |
| Cyril | ano | ano | ne |
| David | ano | ne | ano |

Teď otázka: Je tu někdo, kdo sbírá mince a známky zároveň? O kom můžeme říct „Ten sbírá známky i mince“? Jsou to vlastně dva výroky, „sbírá známky“ a „sbírá mince“, a výsledek je pravdivý pouze tehdy, když oba výroky platí. Tedy musí platit, že „sbírá známky = ano“ a „sbírá mince = ano“. Koukneme do tabulky a vidíme: Cyril je ten pán!

A teď otázka číslo dva: Je mezi pány někdo, kdo sbírá známky nebo krabičky od zápalek? Jsou to opět dva výroky, „sbírá známky“ a „sbírá krabičky“, ale tentokrát nechceme, aby dělal nutně obojí naráz, stačí nám _alespoň jedna varianta_. Z tabulky vyplývá, že podmínku splňují pánové Adam, Cyril a David. Bořek ne, ten sbírá mince.

Otázka tři: Je mezi pány někdo, kdo nesbírá mince? Tedy o kom platí, že „sbírá mince je nepravda“? Ano, máme tu takového pána, Adama.

Ta první otázka ukázala logický operátor AND (tedy „a“, „i“). Výsledek je pravda tehdy a jen tehdy, pokud jsou jednotlivá tvrzení pravdivá.

Druhá otázka ukazovala operátor OR (tedy „nebo“ ve slučovacím tvaru). Výsledek je pravda tehdy, když je pravda alespoň jedno tvrzení. Pozor, nepleťte si to s tím druhým tvarem, vylučovacím, tedy buď – anebo! Tomu říkáme „vylučovací NEBO“ a značíme ho XOR. K němu se ještě dostaneme. _Mimochodem, víte, že v češtině se mezi těmito tvary rozlišuje? Když napíšu „dáte si brambory, nebo rýži?“ – s čárkou před „nebo“ – znamená to, že platí jen jedna varianta. Buď brambory, nebo rýže. To je „vylučovací, exkluzivní OR“ (XOR). Když ale napíšu „podíváte se se mnou na rezistory, kondenzátory nebo diody“, znamená to, že mohou nastat všechny varianty, a to je to naše „obyčejné“ OR._

Třetí otázka ukazovala operátor NOT. Jeho výsledek je pravda, pokud je tvrzení nepravdivé.

Programátorům toto určitě připadá jako jasné a samozřejmé. Ale pro jistotu jsem to rozepsal.

AND se nazývá taky „logický součin“, OR „logický součet“ a NOT je „negace“. Čímž se odkazujeme k matematice: AND nahradíme násobením, OR sčítáním, místo „pravda“ použijeme 1, místo „nepravda“ použijeme 0\. Někdy se můžete setkat i se zápisem pomocí matematických značek ⋁ a ⋀ (NEBO, A).

Uděláme si tabulku pro dvě proměnné, A a B, a výsledky funkcí AND a OR:

| A | B | A OR B | A AND B |
| --- | --- | --- | --- |
| 0 | 0 | 0 | 0 |
| 0 | 1 | 1 | 0 |
| 1 | 0 | 1 | 0 |
| 1 | 1 | 1 | 1 |

Máme čtyři možné kombinace, do jakých se vstupy mohou (legitimně) dostat. Z tabulky je vidět, že obě funkce jsou komutativní, to znamená, že když jim prohodíte hodnoty A a B, bude to jedno.

Třetí logická funkce do party je NOT, též logická negace (značí se ¬ před parametrem, nebo vodorovnou čárou nad výrazem) – je to funkce s jedním parametrem a jednou hodnotou, a pokud je parametr 0, je hodnota 1 a obráceně:

| A | NOT A |
| --- | --- |
| 0 | 1 |
| 1 | 0 |

Negované signály se značí různými způsoby. Nejčastěji tak, že nad názvem signálu je vodorovná čárka: Q a Q Nadtržení se ale zapisuje velmi nepohodlně, proto se někdy setkáte s tím, že negovaný signál bývá označen lomítkem: /Q. Tohoto zvyku se přidržím i já. Další možnost je označit takový signál písmenkem „n“ – nQ, nREADY, nBUSY…