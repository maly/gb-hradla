## 18.7 Zakázané kombinace, zpětná vazba, … {#18-7-zak-zan-kombinace-zp-tn-vazba}

Pojďme si říct na rovinu, že zpětná vazba je dobrý sluha, ale zlý pán. Může snadno způsobit to, že se celý obvod rozkmitá, začne fungovat úplně podivně, popřípadě přestane fungovat, a výsledek nebude předvídatelný. Zpětná vazba totiž do krásně deterministického světa kombinačních obvodů, kde je stav výstupů závislý jen a pouze na stavu vstupů, zavádí prvek zpětného působení výstupů na vstupy, a pokud vytvoříme něco jako „smyčku“, vznikne nám obvod, jehož stav na výstupech není závislý jen na samotných vstupech, ale i na předchozím stavu obvodu.

Ovšem tahle vlastnost není vždy jen negativní.

Zpětná vazba je v elektronice, v číslicové technice i ve spoustě dalších oborů velmi užitečná. Na jednu stranu způsobí třeba to, že mikrofon strčený před zesilovač vygeneruje hnusné hlasité pískání, na druhou stranu když je vhodně zkrocená, tak může generovat pravidelné (i nepravidelné) impulsy a můžeme s ní navrhnout prvek, který si něco pamatuje. _(Ano, tušíte správně, základ všech polovodičových pamětí je zde!)_

Na to, abychom takové obvody drželi zkrátka a aby fungovaly tak, jak si představujeme, je potřeba dodržet určitá pravidla sebekázně. Minule jsme si ukázali, že u klopného obvodu R-S (Reset / Set) existuje takzvaný „hazadrní stav“, totiž takový, v němž jsou oba vstupy aktivované a oba výstupy mají stejnou hodnotu. Pokud z takového stavu přepneme naráz oba vstupy do neaktivního stavu, nelze říct, v jakém stavu se bude obvod nacházet.

Nejprve si rozšíříme náš klopný obvod R-S o takzvaný povolovací vstup E (Enable). Uděláme to jednoduše – na vstupy R a S připojíme hradla, která propustí řídicí signály R a S pouze v případě, že vstupní signál E bude log. 1:

![222-1.png](images/000364.png)

Vidíte sami – do vlastního klopného obvodu se nedostane nic, pokud je E rovno 0\. Pokud nastavíme E na 1, funguje obvod jako vždycky.

TIP: Tento postup si zapamatujte. Vždy, když potřebujete nějaký vstup, aktivní v logické 1, ošetřit tak, aby fungoval „jen někdy“, použijte předřazené hradlo AND, a do něj zaveďte daný signál a řídicí (povolovací) signál E.

Máme teď hradlo R-S s povolovacím vstupem, ale to nijak neřeší hazardní stav (R = S = 1). Zkuste přemýšlet – jak zařídit, aby nikdy nenastal stav, že R i S budou zároveň v logické 1? Tak samozřejmě, můžeme zapojit mezi oba vstupy hradlo AND, jehož výstup bude zároveň ovládat vstup E tak, že pokud nastane R = S = 1, tak vstup E zavře... Nějak takto:

![222-2.png](images/000408.png)

Což je řešení, které téměř nemá chybu. Ve skutečnosti má chybu zásadní, a to tu, že řídicí signál vzniká až v hradle NAND. A hradlo má, jak už víme, nějaké zpoždění, takže hazardní stav R = S = 1 projde přes obě hradla o chviličku dřív, než je stihne nula na výstupu E „zabouchnout“.

Použijeme tedy jiný trik: zrušíme dva vstupy R a S, a budeme používat jen jeden. Ten připojíme na oba vstupy – na vstup S přímo, na vstup R přes invertor. Takový vstup nazveme D (jako že „data“). Pokud bude D = 0, bude S taky rovno 0 a R rovno 1\. Pokud bude D = 1, bude S = 1 a R = 0\. A takto vygenerované signály pošleme do obvodu spolu s povolovacím vstupem E, jak jsme si ho ukázali výše. Výsledkem je obvod, který se označuje jako latch – česky se překládá jako „závora“, ale tenhle pojem se moc neujal, a i v češtině se říká latch, ale vyslovuje se to [leč].

![223-1.png](images/000184.png)