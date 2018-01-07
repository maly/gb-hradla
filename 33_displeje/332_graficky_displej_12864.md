## 33.2 Grafický displej 12864 {#33-2-grafick-displej-12864}

Předchozí displeje byly znakové. Sice interně používají matici bodů pro každý znak, ale kromě možností nadefinovat si několik málo znaků „po svém“ nemáte jak zobrazit třeba graf.

Tuto nevýhodu odstraňují grafické displeje. Pokračovatelem výše uvedených displejů je displej 12864 – číslo udává, že má rozlišení 128 × 64 bodů.

![372-1.jpeg](images/00413.jpeg)

Tyto displeje jsou opět jednobarevné, nejčastěji černá kresba na pozadí podsvíceném bíle nebo zeleně, popřípadě bílá kresba na modrém pozadí… Rozhraní je většinou podobné předchozím modelům, ale některé displeje mají možnost přepnout se do sériového rozhraní (SCK + MOSI). Samozřejmě existují i expandéry – moduly, které tyto displeje připojí na sběrnici I2C.