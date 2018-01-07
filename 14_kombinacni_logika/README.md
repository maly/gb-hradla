# 14 Kombinační logika {#14-kombina-n-logika}

Je fajn, že nám jedno hradlo dělá jednu funkci, ale to není moc zajímavé. Zajímavé to začne být, až když si ty vývody začnete všelijak spojovat. U obvodů 74xx platí, že k jednomu výstupu můžete připojit až deset vstupů. Výstup ale nikdy nesmíte připojit přímo k jinému výstupu. Pokud chcete dva výstupy nějak spojit dohromady, (skoro) vždycky musíte použít hradlo.

Proč nesmíte spojit výstupy přímo spolu? Ještě se k tomu vrátím, ale teď dovolte aspoň stručné vysvětlení: Když budou oba v logické 1 nebo oba v logické 0, tak by to teoreticky nemuselo vadit. Jenže co když výstup jednoho hradla bude logická 1 a výstup druhého logická 0? Jaký bude výsledek? „Logická polovina“ neexistuje… Ve skutečnosti bude výsledek takový, že zbůhdarma poteče proud skrz jedno hradlo do druhého a výsledek bude nejasný.

Hradlo je součástka, která _realizuje_ logickou funkci. Základní logické funkce jsou, znovu připomínám, AND, OR a NOT. Jejich vhodnou kombinací lze získat všechny logické funkce. V praxi se používá hradlo NAND (popřípadě NOR), z nějž lze poskládat všechny ostatní. Vážně, hned si to ukážeme.

Proč _hradlo_? Hradlo je pojem z železnice. Do jeho přesné definice se pouštět nebudu, to by mě případní železničáři mezi vámi utloukli. Zůstanu u jednoduchého lidového popisu: Hradlo je _ten semafór_, který říká v zásadě buď „volno“, nebo „stůj“. Obvod s funkcí AND vlastně může hrát roli takového „hradla“ pro logický signál. Na jeden vstup, nazvu ho datový, přivedu kýžený signál, a druhým řídím. Když je řídicí vstup 0, je na výstupu taky nula. Když je na řídicím vstupu jednička, je na výstupu to, co je na datovém vstupu.

Zkusme si to na nepájivém poli:

Jedno tlačítko pro nás bude „signál“, druhé tlačítko „povolení“. Ale musíme počítat s tím, že výsledek je negovaný, takže pokud je „povolení“ nula, bude na výstupu vždy 1, pokud je „povolení“ 1, bude na výstupu negovaný signál.

Chcete poradit trik, jak diodou zobrazovat negovaný výstup? Zapojte ji ne k zemi, ale k napájecímu napětí! Samozřejmě je nezbytné, aby byla správně polarizovaná… Pak bude svítit, když na výstupu hradla bude logická 0.

Zkuste si to takto přepojit, uvidíte, že teď bude LED svítit přesně opačně, tedy ve stavu 0.

![156-1.png](images/000132.png)

A když už v tom budete, podívejte se, co se stane, když použijete jen jedno tlačítko, a to připojíte:

a. na oba vstupy NAND najednou

b. na jeden vstup NAND, a na druhý zapojíte napevno zem (GND)

c. na jeden vstup NAND, a na druhý zapojíte napevno napájecí napětí (Vcc)