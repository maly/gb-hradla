## 20.4 Další čítače {#20-4-dal-ta-e}

Ukázali jsme si zatím takzvané asynchronní čítače – na vstup je přivedený signál, a ten se postupně šíří vnitřními klopnými obvody z jednoho do druhého. Takže se hodnota mění sice rychle, ale přesto postupně, což může někdy vadit. Proto se v takových situacích používají takzvané synchronní čítače – ty mají zavedený jednotný časový signál pro všechny stupně, takže se všechny výstupy mění naráz.

U obvodu 7490 jsme viděli kromě nulovacích vstupů R0 i nastavovací vstupy R9\. Obecnější verze čítačů umožňuje nastavit libovolnou hodnotu – říká se tomu „čítač s přednastavením“ (preset).

Některé čítače umí čítat nahoru (0 – 1 – 2 – 3 – 4 …) i dolů (7 – 6 – 5 – 4…).

Kombinací všech zmíněných funkcí oplývají čítače 74192 a 74193\. Opět jde o čtyřbitové čítače – typ 193 je binární, typ 192 desítkový.

![258-1.png](images/000245.png)

Obvod má dva hodinové vstupy, CountUp a CountDown. První funguje jak jsme zvyklí a vyvolává čítání vzhůru. CountDown vyvolává čítání dolů. Čítače mají čtyři výstupy: QA, QB, QC, QD. Navíc mají i výstupy „/Carry“ a „/Borrow“ – /Carry označuje, že čítač příštím pulsem přejde ze stavu 15 do stavu 0 (respektive ze stavu 10 do stavu 0 u desítkového). Signál je negovaný, takže tuto skutečnost oznámí, logicky, nulou. Podobnou funkci má signál /Borrow – oznamuje, že čítač je ve stavu 0, a při dalším pulsu CountDown přejde na nejvyšší hodnotu (15, resp. 10). Tyto výstupy se používají k řetězení čítačů za sebe, pokud chcete získat vícebitový čítač.

Další vstup je známý nulovací vstup, zde označený CLR – Clear. Vynuluje celý čítač.

Poslední pětice vstupů jsou vstupy A, B, C, D a /LOAD. Signál /LOAD říká, že se do čítače má zapsat hodnota ze vstupů A, B, C, D. A protože je /LOAD negovaný, děje se tak při změně úrovně z 1 (klidový stav) do 0 (aktivní stav).

Vím, že někdy obrázek vydá i za 273 slov, tak se podívejme, jak funkci obvodu 74193 popisuje graficky datasheet:

![259-1.png](images/000320.png)

No dobře, uznávám, tento obrázek není právě krystalickou ukázkou, ten v hlavě začátečníka vydá sice za 273 slov, ale většina z nich je „cože?“ Ale protože takových obrázků jsou plné datasheety, pojďme tomu dát trochu práce.

V grafu jsou vyznačeny časové průběhy signálů. Vlevo jsou signály popsané – máme tam CLR, /LOAD, datové vstupy, výstupy, signály UP a DOWN a výstupy přenosu. Graf zachycuje průběhy ve významných okamžicích – neznamená to, že to takto musí jít za sebou, to ne!

Jako první je událost CLEAR. Vidíte, že nastala příchodem pulsu na vstup CLR a měla vliv na výstupy QA až QD. Ty předtím mohly mít jakýkoli stav (naznačeno přerušovanou čárou v log. 1 i log. 0), ale jakmile přišla vzestupná hrana CLR, tak se na těchto výstupech nastavila 0.

Vedle je popsána událost PRESET. Všimněte si, že CLR je v log. 0 a přišla sestupná hrana na vstupu /LOAD. S ní se výstupy QA až QD nastavily podle stavu na vstupech A až D. (Tady je to trošku nejednoznačné, protože stejné úrovně jsou nakreslené na vstupech i pro událost CLEAR; správně by měly být čárkované, protože na nich při nulování nezáleží.)

Další události, jaké jsou znázorněné, probíhají při CLR = 0 a /LOAD = 1\. Na hodnotě vstupů A – D nezáleží. Nejprve se ukazuje, co se děje při pulsech na vstupu UP (= čítání nahodu, count up), poté co dělají pulsy na vstupu DOWN. Sledujte, jak se mění hodnoty na výstupech, všimněte si hlavně _kdy_ se mění (při vzestupné hraně signálů UP a DOWN), všimněte si, _jak_ reagují signály /CO a /BO (přenos, resp. výpůjčka)…