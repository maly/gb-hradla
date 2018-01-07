## 30.2 Špinavej trik {#30-2-pinavej-trik}

Zastávám názor, že vynaložené úsilí by mělo být úměrné očekávanému výsledku, a že věci by měly být funkční a _dobré dostatečně pro zamýšlené použití_. Jinými slovy – když stavím zeď, nebudu si brát mikrometr, abych všechno důkladně změřil. Když budu měřit venkovní teplotu, nebudu kvůli tomu pořizovat ultrapřesný teploměr s přesností 0,01 °C. A když si stavím pro radost, tak použiju to, co:

• vyhovuje mým potřebám,

• dá se to dobře koupit,

• už to někde někdo zkusil, použil a napsal o tom.

Tedy v případě meteostanice budu chvíli googlit a zjistím, že lidé nejčastěji používají součástky, co se jmenují DHT11 nebo DHT22 (měří vlhkost a teplotu) a BMP180 (měří teplotu a atmosférický tlak). Zjistím, že pro ně jsou desítky příkladů, jak je zapojit k Arduinu, a taky to, že jsou velmi snadno dostupné v e-shopech jako moduly, které stačí propojit vodičem s Arduinem, a dají se i naskládat na nepájivé kontaktní pole.

Jasně, profesionální zařízení bych takto nestavěl – ale nikdo tu nemluvil o profesionálním zařízení. Od začátku je tu řeč o nadšeneckém kutění pro radost.

Tento přístup vyvolává v některých opravdových odbornících záchvaty agresivního odporu: „je to čuňárna, to není elektronika, to je takové náhodné patlání něčeho, co najdu na webu, ten člověk si říká elektronik, ale ve skutečnosti tomu nerozumí…“ Na druhou stranu můžete díky tomuto přístupu rychle vyzkoušet nějakou myšlenku, nápad, ověřit, jestli to bude fungovat, postavit prototyp, a celé to zvládnete za jedno odpoledne.

Důležitou poznámku tu ale udělám: Když studujete na webu nějaké cizí zapojení či kód, asi začnete tím, že to zkopírujete a zkusíte spustit. Ale pak následuje velmi důležitá část, a tu nepřeskakujte: Snažte se pochopit, co se tam děje a jak to funguje!

Když autor použije někde tranzistor, ptejte se sami sebe: jakou tam má funkci? Co by se stalo, kdyby… Mohl bych použít nějaký jiný? A když tady čeká 10 milisekund, proč to tak je? Jaký měl důvod, že čeká? A můžu to zapojit na jiné piny?

Klást si otázky a odpovídat na ně je to nejcennější, co můžete s cizími příklady udělat. Tupě okopírovat to dokáže i cvičená opice. Já vás ale prosím, apeluju, naléhám na vás a žádám vás: Nedělejte to! Vždy berte nějaký hotový příklad jako inspiraci pro vlastní experimenty. Do cizích knihoven se podívejte, abyste viděli, co se děje pod kapotou. Držte se tohoto přístupu, a věřte mi: naučíte se spoustu věcí, a bude to zábavné učení.

Ostatně, i sami profesionálové staví také z ověřeného – když je potřeba zesílit audiosignál, použijí „zapojení první volby“, tedy tranzistor se společným emitorem, vyzkouší, ověří, a pokud nevyhovuje, tak teprve vymýšlejí jiná důmyslná zapojení.