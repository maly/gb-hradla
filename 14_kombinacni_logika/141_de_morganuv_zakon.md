## 14.1 De Morganův zákon {#14-1-de-morgan-v-z-kon}

Ve skutečnosti, věřte mi nebo ne, si v celé číslicové technice vystačíte s jedním jediným typem hradla! Vše ostatní si z něj dokážete poskládat. Tímto hradlem je nejčastěji NAND (mohl by teoreticky být i NOR). Všimněte si tabulky obvodu NAND a přemýšlejte: Co se stane, když spojíte oba vstupy dohromady a na oba přivedete stejnou hodnotu? Jak se bude obvod chovat? Podívejte se na první a poslední řádek tabulky – nepřipomíná vám to nic?

_No jasně, získáte tak invertor!_

Zkuste si to:

![157-1.png](images/000312.png)

Tlačítko S2 je teď úplně „plonkové“, bez funkce (jen zahřívá rezistor R2). Tlačítko S1 obsluhuje oba vstupy.

A když zapojíte takový invertor na výstup hradla NAND? Tedy použijete dvě hradla…

![157-2.png](images/000135.png)

Zapište si zase výsledky do tabulky:

| A | B | Y |
| --- | --- | --- |
| 0 | 0 |  |
| 0 | 1 |  |
| 1 | 0 |  |
| 1 | 1 |  |

Jistě už víte, co to je za funkci.

A co když invertujete vstupy hradla NAND? Jaký bude výsledek? (Napovím: všimněte si v tabulce podobnosti mezi sloupcem NAND a dalšími sloupci... A všimněte si, že při invertování A a B dostanete tutéž tabulku, ale pozpátku...)

![158-1.png](images/000043.png)

A naměřené výsledky hned do tabulky:

| A | B | Y |
| --- | --- | --- |
| 0 | 0 |  |
| 0 | 1 |  |
| 1 | 0 |  |
| 1 | 1 |  |

[eknh.cz/mrgn](https://eknh.cz/mrgn)

Tomu, co jste si teď prakticky zkusili, zapsali a zjistili, se vznešeněji říká _de Morganovy zákony_, a formulují se takto: Negace součinu je rovna součtu negací, negace součtu je rovna součinu negací. Když se vrátíme k matematickému zápisu:

¬ A ⋀ ¬ B = ¬ (A ⋁ B) – - NOT A AND NOT B = NOT (A OR B)

¬ A ⋁ ¬ B = ¬ (A ⋀ B) – - NOT A OR NOT B = NOT (A AND B)

My si z toho můžeme vzít jednoduché ponaučení: z NAND se invertováním vstupů stane OR, z NOR se invertováním vstupů stane AND.