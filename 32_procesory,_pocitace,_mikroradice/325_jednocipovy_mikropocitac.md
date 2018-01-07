## 32.5 Jednočipový mikropočítač {#32-5-jedno-ipov-mikropo-ta}

Sedíte, držíte v ruce Arduino a říkáte si: _Jak ono to funguje? Je tam taky nějaký procesor._

_Jenže, jak ten procesor ví, co má dělat? Musí tam být někde uložený program, v nějaké paměti? A kde je ta paměť?_

_Že by to bylo všechno v tom jednom obvodu? ATmega328P je tam napsáno… Někde jsem četl, že se tomu říká_ jednočip _– co to vůbec znamená?_

Vězte, přátelé, že jste na správné cestě. V minulých kapitolách jsme si ukázali, jak funguje číslicový počítač. Je tam procesor, paměti, periferie… Logický vývoj tedy směřoval k tomu, že výrobci tyto části spojili, vytvořili na jednom čipu a ten strčili do jednoho pouzdra. A protože jsou základní části počítače, tj. procesor, paměti a periferie, na jednom čipu, říká se tomu „jednočipový mikropočítač“. Familiárně pak _jednočip_. Když budete hledat materiály v angličtině, nenechte se zmást: neříká se tomu singlechip, tohle slovo je vyhrazené pro něco trošku jiného, ale označení je microcontroller, v počeštěné podobě pak _mikrokontrolér_ či _mikrořadič_.

Mikrokontroléry vznikly jen pár let po prvních mikroprocesorech. Většinou integrovaly existující procesor v nějaké modifikované podobě spolu s pamětí ROM a malou pamětí RAM, a k tomu i několik periferií, nejčastěji paralelní a sériové rozhraní a čítače / časovače. Ze začátku se vyráběly hlavně mikrokontroléry s paměťmi ROM a PROM, později i EPROM. Logicky s vývojem technologie přišly jednočipy s pamětí FLASH, a ty jsou dnes asi nejrozšířenější.

### 31.5.1 Harvard vs von Neumann {#31-5-1-harvard-vs-von-neumann}

Tady je dobré místo na odbočku. Když jsme se bavili o tom, že paměť obsahuje program, který procesor vykonává, není to tak úplně jednoznačné. Existují dvě hlavní architektury, totiž von Neumannova, kde je operační paměť společná pro program a data, a harvardská, kde jsou paměti pro data a pro program oddělené. U jednočipů je častější architektura harvardská, u počítačů pro všeobecné použití zase von Neumannova.

U jednočipu, třeba toho arduinského ATmega328, je paměť RAM tedy určena pro ukládání zpracovávaných dat a zásobník, kód je v paměti FLASH (tedy de facto ROM). Vzhledem k tomu, že mikrokontroléry jsou primárně určené k tomu, aby dělaly jednu jedinou úlohu, která se po dobu jejich „života“ v daném zařízení nijak výrazněji nemění, tak je harvardská architektura docela vhodná. S touto architekturou můžete pro data a pro program zvolit také rozdílné typy pamětí – třeba mikrokontroléry PIC od Microchipu ze základní a střední řady (PIC10 – PIC16) zpracovávají osmibitová data, ale instrukce mají 12, resp. 14 bitů. Paměť FLASH je menší při stejné kapacitě než paměť SRAM, proto je ekonomičtější a výrobci tím snižují náklady.
