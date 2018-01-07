# 4 Zdroje napětí {#4-zdroje-nap-t}

Ono se řekne – zdroj napětí! Ale jaký zvolit?

V číslicové technice potřebujeme nejčastěji napětí 5 voltů, navíc poměrně stabilní, bez výrazných výkyvů. Při nižším napětí nemusí naše zapojení fungovat, při vyšším se bude přehřívat, a může se i zničit. Kde ale napájecí napětí sehnat?

Jedna z možností je využít počítač a USB, popřípadě využít nejrůznější nabíječky k mobilním telefonům s rozhraním USB. Jejich výhoda je, že dokáží dát docela velký proud a stabilní napětí. Drobná nevýhoda je, že konektor většinou nelze zapojit do nepájivého kontaktního pole (NKP), a je potřeba vše řešit nějakou redukcí.

Pro NKP existují různé moduly, které lze koupit v kamenných obchodech i v e-shopech, a ty se starají o správné rozvedení napájecího napětí a jeho úpravu. Většinou obsahují stabilizátor, přepínač napájecího napětí 5 V / 3,3 V a napájecí konektor – většinou souosý pro různé adaptéry, a k tomu konektor USB.

![087-1.jpeg](images/00031.jpeg)

Problém s těmito moduly je, že když do nich přivedete 5 voltů z USB, tak si stabilizátor vezme nemalou část a na výstupu, kde má být pět voltů, naměříte třeba 3,5 V. Což může být problém. Pokud chcete takový modul používat, pořiďte si k němu raději nějaký adaptér, který dá na výstupu okolo 7-9 voltů. Pokud použijete třeba 12 V adaptér, budou se stabilizátory intenzivně zahřívat.

Další možnost je využít baterie. Nejčastěji používané typy jsou AA / AAA monočlánky. Existují držáky, které spojují dva, tři či čtyři monočlánky sériově, takže výsledkem jsou 3 V, 4,5 V nebo 6 V. Obvody, které používáme, by měly bez problémů fungovat i při 4,5 voltech. Nevýhoda baterií je ta, že jejich kapacita je omezená, a po několika dnech zkoumání, zkoušení a testování se zkrátka vybijí. Nabíjecí monočlánky pomohou jen trochu – po několika dnech zkoumání, zkoušení a testování se vybijí taky, ale můžete je nabít. A nezapomeňte, že tyto monočlánky mají o něco nižší napětí, jen cca 1,2 voltu. Čtyři takové, zapojené sériově (tedy za sebou) dají dohromady 4,8 voltů. Pokud budete experimentovat intenzivněji, doporučuju pořídit si nějaký zdroj, napájený ze sítě.

![088-1.jpeg](images/00039.jpeg)

Některá zařízení, vybavená vhodným měničem napětí, lze napájet i z destičkové baterie, která dává 9 voltů. Takové baterie se používají často k napájení např. multimetrů. Existují k nim konektory, které lze připojit například k výše zmíněným napájecím modulům. Ale napájení z takových baterií je vysloveně nouzové, protože pokud nemáte zapojení, navržené speciálně na malý odběr, tak kapacita takové baterie vystačí jen na pár hodin provozu.

![088-2.jpeg](images/00048.jpeg)

Pokud vás elektronika zaujme víc, určitě si pořiďte laboratorní zdroj, u kterého můžete regulovat napětí i proud. Nemusí to být hned profesionální zařízení za několik tisíc Kč, vystačíte i s levnější variantou. Dbejte na to, aby zdroj dokázal dát alespoň 15 voltů a proud 1 A.

Zajímavá možnost je využít zdrojů pro počítače PC s konektorem ATX. Existují adaptéry pro tyto konektory, ze kterých pak lze odebírat napětí 5 V, 12 V i - 5 V. Dbejte na to, aby takový zdroj měl vždy nějaký minimální odběr – zapojte například na napájecí napětí žárovku. Pokud necháte ATX zdroj bez zátěže, přetíží se a shoří! _No dobře, nebude hořet jasným plamenem, spíš tak jako zasmrdí a přestane fungovat. Důvodem je, že tyto zdroje jsou zapojeny jako takzvané „spínané zdroje“, a v nich slouží cívka jako akumulátor energie, z níž se odebírá přesně dané napětí. Výhodou těchto zdrojů je jejich velmi dobrá účinnost, nevýhodou to, že vyžadují zátěž, která energii z cívky odvede a zpracuje. Pokud ji neodvede, naakumulovaná energie se začne, laicky řečeno, spalovat přímo v cívce._

![089-1.jpeg](images/00010.jpeg)