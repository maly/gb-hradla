# 31 Bezdrátový přenos dat {#31-bezdr-tov-p-enos-dat}

Bezdrátový přenos můžete zařídit několika různými způsoby. Většinou se pod pojmem „bezdrátový“ myslí nějaký přenos pomocí radiových vln, i když technicky vzato do bezdrátového přenosu dat patří i třeba infračervený (znáte z vašich televizí) nebo ultrazvukový. Ale teď se chci věnovat radiovému přenosu.

Já se v této knize záměrně nechci věnovat vysokofrekvenční elektrotechnice – to je tak složitý a komplexní obor, že ho rád nechám stranou. To by ta kniha měla dvojnásobný rozsah…

Naštěstí můžete používat i věci, u nichž neznáte princip fungování. A pokud vám někdo říká, že ne, nevěřte mu, protože to byste nemohli ani zapnout automatickou pračku. Pro začátek stačí vědět, jak to použít a jaké jsou pravidla a limity.

Rádiové vlny patří, stejně jako třeba rentgenové paprsky, mikrovlny v troubě, světlo nebo ultrafialové záření mezi elektromagnetické vlnění. Možná vás to překvapí, ale princip rádiových vln a třeba světla je obdobný, liší se pouze svou frekvencí.

Někdy se setkáte také s označením „dlouhá vlna, krátká vlna“ apod. Má to spojitost s šířením elektromagnetických vln a jejich frekvencí. Délka vlny je technicky vzdálenost, kterou elektromagnetické vlnění urazí během jednoho „kmitu“. Čím vyšší kmitočet, tedy čím víc kmitů za sekundu, tím je kratší vlna. Elektromagnetické vlnění s frekvencí 299 MHz má tedy délku vlny zhruba 1 metr, rádiové vysílání v pásmu FM (87 – 108 MHz) má vlny délky (přibližně) 2,7 až 4 metry.

Viditelné světlo má frekvenci tak vysokou, že by bylo už nepraktické udávat ji v hertzech (přesněji v petahertzech, 1015), místo toho se používají praktičtější nanometry (zhruba 390-760 nm je pásmo viditelného světla, červené má vlnu nejdelší, tedy frekvenci nejmenší, směrem k fialové délka klesá, frekvence roste).

Zůstaneme ale u rádiových vln. Udělat vysílač, který bude vysílat rádiové vlny, není těžké. Stačí k tomu kousek drátu a přesně vyladěný oscilátor. Jenže vysílání není jen tak. Protože rádiové vlny využívá televize, rozhlas, záchranáři, armáda a kdoví kdo ještě, jsou pečlivě rozdělené do pásem a je určeno, kdo smí jaké frekvence používat. Pokud chcete provozovat rádiový vysílač, musíte mít přidělenou frekvenci. Tím je zajištěno, že nebudete nikoho rušit a nikdo nebude rušit vás. Když budete vysílat bez přidělené frekvence, poměrně brzy si na vás patřičné úřady posvítí.

Naštěstí existuje několik frekvenčních pásem, v nichž může používat rádiové vysílání každý, i bez patřičné licence, pokud dodrží některá pravidla, především maximální vysílací výkon. Říká se jim „rádiové kmitočty vymezené všeobecným oprávněním“, a vy si prosím pamatujte, že to jsou hlavně tato pásma:

• 27 MHz pro „CB stanice“ (Citizen Band – občanské pásmo),

• 433 MHz pro přenos dat,

• 868 MHz pro přenos dat (v USA se používá 911 MHz, pozor na to!),

• 2,4 GHz a 5 GHz pro přenos dat (např. WiFi).

Na těchto frekvencích byste neměli mít s homologovaným přístrojem, to podtrhuju, žádný problém. Frekvence 433 a 868 jsou nejčastější frekvence, které můžete pro vlastní konstrukce použít. Doporučuju nevynalézat kolo a nesnažit se navrhnout vlastní vysílací a přijímací modul! Kupte si hotové a existující, které dodržují frekvenci i maximální výkon.

Počítejte s tím, že povolený výkon vám postačí pro pokrytí oblasti v řádech desítek metrů na volném prostranství. Je to proto, abyste svým provozem nerušili ostatní. Rádiová frekvence je holt sdílený statek, něco jako společná místnost: hlasitý hovor dvou lidí bude rušit váš hovor s někým dalším. Proto se tato pásma dělí do přesnějších _kanálů_… Například v pásmu 433 MHz má kanál 1 frekvenci 433,075 MHz, kanál 2 má frekvenci 433,100 MHz, kanál 3 má 433,125 MHz atd., až kanál 69 má frekvenci 434,775 MHz. Teoreticky byste měli mít možnost naladit vysílač i přijímač na přesný kanál v rámci daného pásma a snížit tak pravděpodobnost, že budete kolidovat například s bezdrátovým zvonkem u sousedů, nebo s ovladačem jejich garážových vrat. Praxe je bohužel ale zase mnohem pestřejší než teorie, protože velké množství hlavně levných zařízení vysílá „jak se dá“, a hlavně v městech jsou tato pásma velmi zarušená vším možným, co na těchto frekvencích vysílá. Kdejaké bezdrátové teploměry, zvonky, ovladače kdečeho…