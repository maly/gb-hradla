## 14.14 Pojďme, budeme už fakt něco počítat! {#14-14-poj-me-budeme-u-fakt-n-co-po-tat}

Ne, vážně – zatím tu děláme samé OR a AND a přepínáme signály zleva doprava, ale ještě jsme nespočítali ani kolik je 6 + 3\. A ne že by to nešlo. Jde to. A jak?

No, budete počítat s dvojkovými čísly. Budete sčítat 0110 (což je 6) a 0011 (což jsou 3). Jste na tom stále líp než staří Římané, kteří sčítali VI + III – to je hrozně nešikovné. Díky pozičnímu zápisu číslic v číslech můžete zapsat pod sebe:

<pre class="kod">+0110</pre>

<pre class="kod">+0011</pre>

<pre class="kod">-----</pre>

<pre class="kod">=????</pre>

Pamatujete se, jak jsme sčítali pod sebou víceciferné sčítance ve škole? Začnete zprava a budete sčítat jednotky s jednotkami:

0 + 1 = 1

Poslední číslice výsledku je tedy 1\. Přesuňte se k vyššímu řádu – v našem případě ke „dvojkám“ (v desítkové soustavě k desítkám). Sčítejte opět pod sebou: 1 + 1 = ? No, v desítkové soustavě to jsou 2, ve dvojkové nemáme dvojku, tak výsledek bude „10“. Jak ho zapíšete? No stejně jako při obyčejném sčítání: zapíšete si nulu, a tu jedničku si přenesete do vyššího řádu (tady „do čtyřek“)

Předposlední číslice je 0 a posouváte se o řád výš, tedy opět doleva. Tady sčítáte 1 + 0, a k tomu musíte připočítat tu jedničku, co jste si přenesli v předchozím kroku: 1 + 0 + 1 = ? Opět tedy ve dvojkové soustavě 10\. A stejný postup – zapíšete nulu, jedničku si přeneste o řád výš.

Třetí od konce tedy je nula, jděte o řád výš, na „osmičky“, a sčítejte: 0 + 0 + 1 (to je přenos z předchozího kroku). Tedy výsledek: 1\. Zapíšete…

Dostali jste tedy 1001 – což je binárně 9 (1 × osmička, 1 × jednička).

Zkuste si:

a. 0110 + 0111

b. 1000 + 1001

c. 1010 + 1111

Máte? Čistě pro kontrolu:

a: 1101 (6 + 7 = 13), b: 10001 (8 + 9 = 17), c: 11001 (10 + 15 = 25)

Tak. A teď si pojďme říct, jak to tedy počítáme pro jednotlivé bity.

Mějme dvě čísla, A a B. Každé z nich bude čtyřbitové. Jednotlivé bity si označíte A3-A0 a B3-B0\. jednotky budou A0/B0, dvojky A1/B1, čtyřky A2/B2 atd.

Na nejnižším řádu sčítáte A0 + B0\. Výsledek si označíte S0, přenos z nejnižšího řádu C0 (C nebo CY = Carry, tedy přenos). Jak bude vypadat tabulka?

| A0 | B0 | C0 | S0 |
| --- | --- | --- | --- |
| 0 | 0 | 0 | 0 |
| 0 | 1 | 0 | 1 |
| 1 | 0 | 0 | 1 |
| 1 | 1 | 1 | 0 |

Schválně se podívejte na sloupce C0 a S0, mělo by vás to do očí uhodit... Už víte?

No jasně! C je přeci obyčejné A AND B, S je A XOR B. Takto vypadá obvod, kterému se říká poloviční sčítačka (anglicky _half adder_).

[eknh.cz/had](https://eknh.cz/had)

U nejnižšího řádu nám stačí, ale už u řádu dvojek budete potřebovat přičíst ještě přenos z nižšího řádu – C0\. Musíte tedy použít plnou sčítačku (anglicky _full adder_). Bude mít tři vstupní signály – An, Bn a vstupní přenos CIn – a dva výstupní: Sn a COn. (CI jako Carry In, CO jako Carry Out). Její obecná funkce se dá popsat následující tabulkou:

| An | Bn | CIn | COn | Sn |
| --- | --- | --- | --- | --- |
| 0 | 0 | 0 | 0 | 0 |
| 0 | 1 | 0 | 0 | 1 |
| 1 | 0 | 0 | 0 | 1 |
| 1 | 1 | 0 | 1 | 0 |
| 0 | 0 | 1 | 0 | 1 |
| 0 | 1 | 1 | 1 | 0 |
| 1 | 0 | 1 | 1 | 0 |
| 1 | 1 | 1 | 1 | 1 |

![o221.png](images/000042.png)

Když se budete na výstupní dvojici CO a S dívat jako na dvoubitové číslo, zjistíte, že jeho hodnota (0 – 3) udává počet jedniček na vstupech A, B, CI. To je zajímavý poznatek, ale vy ho potřebujete převést nějak do řeči hradel. Můžete na to jít od lesa, prohlásit, že Y je vlastně (A XOR B), a pokud je CI = 1, tak je to negované. Schválně, máme takovou funkci, která by dělala něco takového, jako že „S = A pokud B=0, a pokud B=1, tak S = NOT A“? Máme?

Máme, a je to, světe div se, XOR. Podívejte se znovu na její tabulku hodnot – vidíte to tam? Takže u plné sčítačky můžete říct, že S = (A XOR B) XOR CI

Co s CO? Tam je to trošku složitější. Pokud CI = 0, tak jde o A AND B, pokud CI = 1, tak jde o A OR B. To moc nepomáhá. Co si to takhle popsat slovy: CO je 1, pokud je zároveň A a B nebo A a C nebo B a C. Výrazem: CO = (A AND B) OR (A AND CI) OR (B AND CI)

Mimochodem, víte, jak jsem psal, že OR se taky označuje jako logický součet a AND jako logický součin? Mohli bychom přepsat výše uvedený výraz do podoby CO = A × B + B × CI + A × CI

Jediný problém je, jak udělat OR se třemi vstupy. Kupodivu docela jednoduše: A + B + C = (A + B) + C.

![177-1.png](images/000395.png)

[eknh.cz/fad](https://eknh.cz/fad)

Tak, a teď je potřeba tohle zopakovat čtyřikrát a získat tak čtyřbitovou sčítačku. Do každé sčítačky zavedete příslušné bity z čísel A a B, a k nim přenos z předchozího řádu. U nejnižšího bude přenos nula, přenos z nejvyššího řádu udělá pátý (nejvyšší) bit výsledku.

![178-1.jpeg](images/00378.jpeg)

Všimněte si, že v rámci zjednodušení jsem výše uvedené zapojení sčítačky z elementárních hradel proměnil v „black box“ – prostě obdélníček, na něm je napsáno „toto je sčítačka“, a k tomu popsané vývody. Uvnitř je to ale pořád to původní schéma.

Výsledný obvod je tak složitý, že se nikomu nevyplatí něco takového stavět. Lepší je koupit to už hotové. Co myslíte, udělal to někdo? Odpověď zní: Ano, a má to označení 74283\. Je v pouzdru se šestnácti vývody, a zapojeno je to takto:

![178-2.png](images/000207.png)

Cin je vstupní přenos do nejnižšího řádu, Cout výstup do řádů vyšších. Díky tomu je možné dvě sčítačky zapojit paralelně tak, aby vytvořily osmibitovou sčítačku, nebo klidně i vícebitovou. Jediný rozdíl je, že výrobce řády nečísluje od nuly, ale od jedničky (A1-A4). Na funkci to ale nic nemění.

Věřte nebo ne, ale uvnitř je to přesně tak, jak jsme si popsali výš:

![179-1.png](images/000018.png)

Můžeme si z toho něco postavit? No jasně, co třeba binární sčítačku?

Vezmeme osm přepínačů, uděláme z nich dvě skupiny po čtyřech, výsledek nám bude zobrazovat pět LEDek… Máte-li po ruce obvod 74283, můžete si to vyzkoušet na nepájivém poli, ale nemáte-li jej, nezoufejte, můžete použít online emulátor.

[eknh.cz/add4](https://eknh.cz/add4)