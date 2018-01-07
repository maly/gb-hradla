## 13.2 Logické funkce {#13-2-logick-funkce}

Programátoři vědí, nebo by alespoň měli vědět, že máme tři základní logické funkce, totiž AND, OR a NOT.

_Moment, moment, neotočil tu někdo víc stran najednou? Ještě v minulé kapitole tranzistory a volty, a najednou logické funkce? Neuteklo mi něco? Pojďme radši popořadě…_

### 13.2.1 Digitální, nebo analogové? {#13-2-1-digit-ln-nebo-analogov}

Analogová elektronika se zabývá _spojitými veličinami_, digitální (též číslicová) veličinami _nespojitými_. Což je hezká školní definice, ale – co si pod tím mohu představit?

Typická analogová veličina je třeba, řekněme, teplota. Teplota plynule roste a klesá, a záleží jen na přesnosti teploměru, jak přesně tuto změnu změříme. Můžeme vidět, že teplota během dopoledne roste: 13 °C, 14, 15, 16, … Pak vezmeme přesnější teploměr, a sledujeme mnohem rychlejší změny: 13,0… 13,1… 13,2… a tak dál. Když si vezmeme ještě přesnější teploměr, můžeme změnu měřit po setinách, ale vidíme, že teplota se mění spojitě, že v přírodě není žádný „daný krok teploty“. (No, ve skutečnosti je, ale hodně malý, takže to můžeme zanedbat a brát teplotu jako spojitou veličinu.)

Naproti tomu například počet nějakých věcí, dejme tomu vajíček, je typická nespojitá veličina. Vajíčko můžete mít jedno, dvě, tři, nebo třeba žádné, ale nemáte 2,7153 vajíčka. Máte buď dvě, nebo tři. Počet, který vyjadřujeme _přirozenými čísly_, je typická nespojitá veličina. Nemění se plynule, ale jakoby „skokově“.

V elektronice můžeme také využívat oba přístupy. Typickou oblastí, kde dlouhou dobu hrála prim analogová technika, je například zpracování zvuku. Všechny ty reprosoustavy, zesilovače, ekvalizéry, efekty, snímače, mikrofony, to všechno pracuje se zvukem, který je ve své podstatě spojitý. (Dnes už to tak úplně neplatí, dnes už se hojně pro zpracování využívají digitální postupy, ale minimálně od zesilovače dál jde o analogovou techniku.)

Do analogové techniky patří také velmi zajímavá oblast, zabývající se nízkofrekvenčními a vysokofrekvenčními signály, jejich zpracováním, filtrováním, patří do ní součástky, zvané operační zesilovače a komparátory, a je to poměrně zajímavá oblast – ovšem mimo záběr naší knihy.

Představte si, že byste chtěli využít nějak téhle techniky k tomu, abyste něco spočítali. Třeba součet, nebo i logaritmus. Dejme tomu, že bychom řekli: Nula je 0 voltů, hodnota 10000 je 10 voltů, tedy jednička bude 1 mV. Dáme dva potenciometry, kterými budeme moci měnit „čísla“ – tedy napětí na výstupu. Pak mějme nějakou součástku (a taková opravdu existuje), která zjistí, že na jednom vstupu je 18 mV, na druhém 278 mV, obě napětí sloučí a na výstupu poskytne 296 milivoltů. Tedy 18 + 278\. Postavit to lze, ale není to tak úplně přímočaré – stačí když se někde nějaký vodič zahřeje víc, jiný méně, změní se odpory ve vedení, a vyjde vám, že 18 + 278 je tak nějak 280, plus mínus deset procent.

Že by takovou techniku nikdo nepoužíval? Ve skutečnosti používaná byla, a tato omezení se musela nějakým způsobem kompenzovat. Stálo to za to, protože analogové počítače, jak se takovým strojům říkalo, dokázaly téměř v reálném čase velmi složité operace, jako derivace a integrace signálu, které se numerickými metodami řešily velmi zdlouhavě. Programovaly se spojováním základních funkčních celků a dokázaly už někdy v 60\. letech řešit složité lineární a nelineární diferenciální rovnice rychleji, než tehdejší číslicové počítače.

Číslicové počítače jsou založené na jiném principu. Nepracují se spojitými signály, ale s takzvanou binární logikou. Binární znamená, že má pouze dvě hodnoty: 0 a 1\. Pak si třeba řekneme, že 0 bude vyjádřené nula volty a 1 vyjádříme pěti volty a že povolíme nějakou toleranci, tak je celkem jedno, jestli na vstupu bude přesně 5 V, nebo třeba 4,75 – výsledek bude stále hodnota „1“.

Jenže pokud budeme mít jen dvě hodnoty, jak třeba můžeme pracovat s přirozenými čísly? Naštěstí přišla matematika se svými číselnými soustavami. Dovolte jen rychlé opáčko: Jsme zvyklí počítat s desítkovou soustavou. Deset proto, že se rodíme s deseti prsty na rukou – a právě prsty na rukou jsou první počítadlo, které máme.

Mimochodem, víte, jak se řekne latinsky prst? Digitus. Prsty byly první počítadlo přirozených čísel. Od toho „digitální“, neboli „číslicové“.

### 13.2.2 Dvojková soustava {#13-2-2-dvojkov-soustava}

V desítkové soustavě používáme deset základních symbolů pro jednotlivé číslice – totiž 0, 1, 2, 3, 4, 5, 6, 7, 8 a 9\. Pokud potřebujeme zapsat větší číslo, desítku, použijeme k tomu poziční zápis a zapíšeme vedle sebe symbol pro desítky a symbol pro jednotky: 10\. A můžeme pokračovat dál, přidávat další jednotky a počítat: 11, 12, 13… až do 19\. Když přidáme další jednotku, tak nám počítadlo jednotek opět „přeteče“, a my tedy o jedničku zvýšíme číslici na pozici desítek: 20\. Pozice tedy zprava stoupají – jednotky, desítky, stovky, tisíce… Každý řád je desetinásobek následujícího.

Já vím, je to elementární, umíme to všichni a denně to používáme, takže nám to ani nepřijde. Ovšem zopakoval jsem to proto, že si na tom můžeme ukázat přepočítávání do jiných číselných soustav. Když jsem chodil do školy, tak jsme někdy v páté třídě přepočítávali mezi různými soustavami, a byla to ta nejdivnější činnost – nikdo z nás netušil, proč to děláme a k čemu to může být dobré. Pokud to ani vy doteď netušíte, tak se to právě teď dozvíte.

Řekli jsme si, že v binární logice máme jen dvě hodnoty: 0 a 1\. Jak pomocí těchto dvou symbolů zapíšeme nějaká čísla? Princip je stejný jako v té naší desítkové soustavě. Dívejte:

Nulu zapíšeme jako 0\. Jasné.

Jedničku zapíšeme jako 1\. Taky jasné.

Dvojku zapíšeme jak? No, další symbol za 1 už nemáme, tak jedeme opět od 0, a použijeme další řád: 10

Trojku tedy zapíšeme jako 11.

Na poslední pozici jsou zase jednotky. Na předposlední nejsou desítky, ale „dvojky“, na pozici před nimi jsou „čtyřky“, před nimi „osmičky“ – tedy řada jde po dvojnásobcích: 1, 2, 4, 8, 16, 32, 64, 128, …

Čtyřka bude tedy 100\. Pětka 101, šestka 110, sedmička 111.

Osmička bude 1000, devítka 1001, desítka 1010…

K zapsání desítky potřebujeme tedy čtyři symboly. Jaké je nejvyšší číslo, které můžeme zapsat čtyřmi symboly? Je to 15, které zapíšeme jako 1111.

K zapsání čísla v rozsahu 0 až 15 potřebujeme tedy čtyři binární číslice. Z anglického výrazu pro binární číslici „BInary digiT“ vzniklo zkratkové slovo „bit“. Čtyři binární číslice, čtyři bity nám tedy stačí pro zápis šestnácti hodnot (proč 16, když nejvyšší je 15? Protože první je nula, druhá jednička, třetí dvojka… a šestnáctá hodnota je 15).

Digitální technika tedy pracuje se signály, uspořádanými do N-tic bitů. Čtveřice bitů pojme pohodlně číslice od 0 do 9, a k tomu ještě šest navíc. Osmice bitů může vyjádřit číslo od 0 do 255\. Dvě osmice, tedy 16 bitů, dokáže vyjádřit celá čísla od 0 do 65535\. Matematicky zapsáno je možných kombinací 2N.

Nejčastěji se budete setkávat s obvody čtyřbitovými a osmibitovými. Vícebitové součástky samozřejmě existují také, ale více bitů znamená více vývodů ze součástky, tedy buď větší pouzdro, nebo menší vývody… Pro amatérské konstrukce jsou vhodné právě ty méněbitové součástky.

### 13.2.3 Šestnáctková soustava {#13-2-3-estn-ctkov-soustava}

Programátoři ji jistě znají, říká se jí také někdy hexadecimální, méně správně „hexa“. Je vhodná právě pro práci s číslicovou technikou, protože dokáže jedním znakem vyjádřit stav čtyř bitů. Jak už víme, čtyři bity mohou mít 16 různých kombinací. K jejich zápisu použijeme číslice 0 až 9 a pro hodnoty 10, 11 atd. použijeme písmena A, B, C, D, E, F.

Osmibitové číslo vyjádříme pouhými dvěma znaky: 00, 2A, 3F, DC, 12\. Aby se čísla nepletla, zapisují se buď s postfixem „h“, nebo s prefixem „0x“. Tedy 0x2A, 0x12, popř. 3Fh, 56h a podobně.

Pokud to stále ještě neumíte, naučte se zpaměti převody mezi hexadecimálními, desítkovými a dvojkovými čísly, alespoň do těch 16\. Vážně.

### 13.2.4 Zpátky k technice {#13-2-4-zp-tky-k-technice}

Když jsme si zopakovali, jak pomocí dvojkové soustavy můžeme přenést diskrétní informaci, pojďme se podívat, jak je to vlastně realizované fyzicky. Už jsem to tu naznačil, tak to pojďme dokončit.

Nejjednodušší způsob, jak vyjádřit logickou informaci pomocí elektřiny, je ten, že jedné logické úrovni bude odpovídat nějaké napětí, jiné logické úrovni napětí jiné. Nabízí se, že logická nula bude 0 voltů, stav bez napětí, a logická jednička pak nějaké konkrétní dohodnuté napětí – třeba + 5 voltů. No a tak tomu je v podstatě doposud.

Ne že by neexistovaly jiné způsoby. Například u jednoho sériového rozhraní je to tak, že logická 0 je definováno jako napětí + 15 voltů proti zemi, logická 1 je napětí - 15 voltů proti zemi. Některé logické obvody byly dřív stavěny tak, že logická 1 byla definována jako záporné napětí, ještě jiné pracovaly s obrácenou logikou, ale nakonec se jako nejpoužívanější uchytily dvě technologie, které zároveň definují onu otázku: „Kolik voltů je logická 1?“
