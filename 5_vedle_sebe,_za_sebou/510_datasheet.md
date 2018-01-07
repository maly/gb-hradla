## 5.10 Datasheet {#5-10-datasheet}

Co je recept pro kuchaře, co jsou noty pro houslistu, to je datasheet pro elektronika. Datasheet se česky nazývá též „katalogový list“. Dřív to platilo doslova – výrobce vydával katalogy součástek (my starší si pamatujeme katalog Tesly Eltos), kde každé součástce, kterou vyráběl, byla věnována jedna či více stran, kde bylo napsané všechno podstatné, co pro práci se součástkama potřebujete. Tedy – teoreticky. Někdy jste byli rádi, když platilo aspoň zapojení vývodů.

Dnes je situace díky internetu o mnoho jednodušší – k téměř libovolné součástce najdete její datasheet (klíčová slova: Google, název součástky, „datasheet“). Na stránkách výrobců bývají i různé vyhledávače a srovnávače, takže když například hledáte vhodnou součástku, můžete si z portfolia vybrat tu nejvhodnější na základě požadavků – třeba napájecího napětí, frekvence, pouzdra, funkce, ceny, …

Každopádně datasheet je klíčová věc, kterou budete potřebovat téměř vždy.

Zkuste si teď cvičně vyhledat pár datasheetů. Pro diodu 1N4004, pro tranzistor BC547, pro integrovaný obvod 74HCT04…

Tyto součástky vyrábí vícero výrobců, proto je můžete nalézt v různých provedeních a s různým obsahem. Některé speciální obvody vyrábí jen jeden výrobce, tam jste odkázáni pouze na jeho dokumentaci.

Co ale v datasheetu zjistíte vždy:

1. Přesné označení typu. Hlavně u integrovaných obvodů je to docela podstatné – 65C02 je něco jiného než 6502C, i když je obojí vlastně jen mírně vylepšené 6502\. Součástí značení je i informace o pouzdru – 74HCT04N je funkčně shodný s obvodem 74HCT04D, ale jeden z nich je v pouzdru DIL (DIP), druhý v pouzdru SO. Pro nás to je podstatný rozdíl, protože zatímco ten první můžeme použít přímo v nepájivém kontaktním poli, ten druhý je určený pro povrchovou montáž pájením, má proto krátké nožičky a do kontaktního pole jej nedostaneme.

2. Informace o tom, který vývod u jakého pouzdra má jakou funkci.

3. Informace o napájecím napětí, o odběru a dalších charakteristikách obvodů a součástek.

4. Důležité informace o maximálních přípustných hodnotách – především napětí, proudu a teploty.

5. U integrovaných obvodů je popsaná jejich funkce, u těch nejsložitějších, jako jsou jednočipy a procesory, může být i informace o programování.

6. U diskrétních součástek bývají k dispozici různé grafy, například změna odporu v závislosti na teplotě apod.

7. Je popsáno chování za určitých standardních hodnot.

8. Pokud je více variant jednoho typu, je popsáno, čím se od sebe liší. Například tranzistor BC547 má tři varianty, A, B a C, které se liší maximálními přípustnými hodnotami napětí a proudů.

9. U složitých obvodů, například klopných obvodů, pamětí či některých digitálních senzorů, je popsán i komunikační protokol a průběhy signálů, ze kterých vyčteme třeba to, v jakém pořadí musí přijít řídicí signály, aby obvod fungoval správně.

Z dobře napsaného datasheetu zkrátka zjistíte vše, co o součástce potřebujete vědět. Třeba:

• Jaký je úbytek napětí na diodě 1N4007?

• Jaký je maximální proud kolektor-emitor u tranzistoru BC547B?

• Je u tranzistoru BC547 uprostřed báze, nebo kolektor?

• Kam se připojuje napájecí napětí u obvodu 74HCT00? Jak velké má být?

V datasheetech najdete i ta čísla, kterými jsem tu v minulých kapitolách šermoval. Pamatujete? 0,7 voltu na diodě, 10 mA proud LEDkou atd.

U některých dostatečně obecných součástek, jako jsou rezistory, keramické kondenzátory nebo obyčejné LED, často datasheet ani nenajdeme, protože nezjistíme typ součástky. Jde vlastně o takovou „bižuterii“. Přesto – zkuste si najít datasheet pro „červenou LED“.

##### 6 Základní elektronické součástky {#6-z-kladn-elektronick-sou-stky}
