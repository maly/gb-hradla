## 34.4 Postavte si třeba… kalkulačku? {#34-4-postavte-si-t-eba-kalkula-ku}

Našel jsem hezké moduly s šestnácti tlačítky a osmimístným displejem, a když jsem přemýšlel, co z nich postavit, napadla mě, logicky, kalkulačka. Dnes existují dva hlavní způsoby stavby kalkulačky… Ne, pojďme si to říct jinak: Existují dva způsoby, jak přijít ke kalkulačce.

Zaprvé: Buď použijete tu, co máte v počítači, v mobilu, v lednici nebo kdekoli jinde, popřípadě si koupíte některou z 572 modelů, co mají v obchodech, vietnamskými večerkami počínaje. Anebo zadruhé – nějakou si postavíte.

My budeme stavět, protože nás baví elektronika. Dnes existují dva hlavní způsoby stavby kalkulačky. Jeden je opravdu retro, při něm použijete staré kalkulačkové obvody (MHB7001, MC14007), druhý je modernistický, pod heslem _pokud to můžu poskládat z hotových modulů z eBay za dolar až pět včetně poštovného, tak to poskládám z modulů!_

_![380-1.jpeg](images/00369.jpeg)_

Já si takhle vyhlédl modul na fotografii. Je tam osm osmisegmentovek a šestnáct tlačítek a připojuje se to přes SPI, tedy tři dráty (+ 2 na napájení). _Až ho budete hledat na eBay či AliExpressu, hledejte „keyboard display TM1638“._

Všimněte si, jak jsem ho k Arduinu připojil.

Na Arduinu najdete speciální konektor s šesti piny (2 × 3), označený ICSP. Je tam + 5 V a zem, jsou tam tři datové vývody (11, 12 a 13) a RESET. Pokud zrovna nehodláte programovat jednočip, tak jsou volné a jsou natvrdo připojené na piny, kde je vyvedené rozhraní SPI.

![381-1.png](images/000349.png)

Zmíněný modul používá k řízení tlačítek a displeje čínský obvod TM1638\. Existuje datasheet, ale v podobné situaci je nejjednodušší podívat se, jestli už není hotová knihovna pro Arduino. Většinou už ji někdo udělal. Stejně jako v tomto případě.

Všechno propojte, z knihovny otevřete příklad tm1638qyf, změňte nastavení vývodů tak, aby odpovídalo našemu zapojení, a spusťte. Nelekněte se, pokud začne displej zuřivě blikat – to je naprogramované demo!

Práce s klávesnicí je jednoduchá: knihovna vrátí šestnáctibitové číslo, kde co bit, to tlačítko. Nejnižší bit odpovídá tlačítku 1, které je „vlevo nahoře“…

Kalkulačka potřebuje 10 tlačítek pro číslice. Zbývá jich 6\. Jedno tlačítko zabere „=“, zbývá jich pět. Takže máme prostor pro čtyři základní matematické operace, a to poslední tlačítko bude „C“ – tedy tlačítko na smazání chyby.

Namapujeme si je takto:

![382-1.png](images/000284.png)

První pokus mi ukázal, že obvod by sice měl odstranit zákmity, ale nějak se mu to nedařilo, takže jsem si je ošetřil sám.

Druhý krok byla jednoduchá funkce: Když zmáčknu tlačítko s číslicí, objeví se na displeji a přidá se k už napsanému číslu. Je to jednoduchá operace: Z = 10 × Z + n. Jestli nevěříte, zkuste si to: Mám na displeji 123, zmáčknu čtyřku, výsledek by měl být 1234, a to je přeci těch původních 123 × 10 + (zmáčknutá) 4! Do téže funkce přidám omezení počtu míst (na sedm, osmou pozici nechám volnou pro symbol „mínus“).

Tlačítko C prostě jen vynuluje pracovní registr (a na displeji se objeví 0).

Až budete implementovat vlastní matematiku, bude se vám hodit pár tipů. Není to úplně triviální, jak by to na první pohled mohlo vypadat. Nezapomeňte, že kalkulačky pracují s infixovou notací, to znamená že 2 + 3 se zadává jako série stisknutí tlačítek 2, +, 3 a =. Algoritmus je tedy takový:

• Pokud uživatel stisknul číslici, přidej ji jako nejnižší řád k tomu, co je na displeji.

• Pokud uživatel stisknul C, nastav displej na 0.

• Pokud uživatel stisknul nějakou operaci, poznamenej si ji. Pak proveď předchozí uloženou operaci, ulož si mezivýsledek do registru X a zobraz ho. Zároveň při dalším stisknutí číslice nejprve vynuluj displej.

• Pokud uživatel stisknul „=“, tak proveď poslední uloženou operaci, výsledek si ulož do registru X a zobraz ho.

K tomu jen poznámka: Kalkulačka nezohledňuje (v téhle verzi) prioritu operátorů, to si můžete vyřešit za domácí úkol.

Kalkulačka potřebuje několik pracovních registrů: jednak registr X na uložení mezivýsledku, pak registr „op“ na uložení zvolené operace, a konečně registr Z, kde je obsah displeje.

Takhle z popisu by to mohlo vypadat, že při stisku tlačítka s nějakou operací se vlastně vykonává ta předchozí, a když se nad tím zamyslíte, tak to tak opravdu je. Ta aktuální se ukládá „na příště“ a provádí se ta předchozí. Tlačítko „=“ je v podstatě stejné jako jakákoli jiná operace, jen s tím rozdílem, že „na příště“ se uloží operace „nedělej nic, jen zkopíruj displej do mezivýsledku!“

Čistě pro formu si zkuste pár cvičení: upravit kalkulačku tak, aby zvládala prioritu operátorů, upravit ji tak, aby umožňovala zadat záporná čísla, upravit ji na RPN, …

RPN (Reversed Polish Notation, obrácená polská notace) je takový zápis matematických operací, kde se nejprve zadávají čísla, a teprve poté operátory. Například 2 + 3 × 4 se s RPN zadá jako 2 3 4 × +. Čísla se průběžně ukládají na zásobník, operátory si ze zásobníku berou argumenty a vrací tam výsledky.

Schéma a zdrojový kód najdete na [eknh.cz/calcuino](https://eknh.cz/calcuino)

##### 35 Osm tlačítek na třech vodičích {#35-osm-tla-tek-na-t-ech-vodi-ch}