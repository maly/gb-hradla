## 32.3 Periferie {#32-3-periferie}

Už několikrát to tu padlo – periferie. Co to vlastně je? Možná napoví český výraz vstupně/výstupní obvody (ostatně i v angličtině se označují jako I/O, tedy Input/Output). Technicky to jsou obvody, které jsou připojené na sběrnici procesoru, a které může procesor adresovat, zapsat do nich požadovaná data anebo naopak data přečíst.

Na rozdíl od paměti, která slouží jako velké úložiště, plné buněk, kam se data ukládají a z nichž se čtou, tak periferie mají podstatně pestřejší funkce. Když chcete k počítači připojit klávesnici, je to periferie. Periferie je třeba sériové rozhraní, nebo externí paměť… Periferie jsou všechny čidla a senzory. Zkrátka vše, co není procesor a pracovní paměť.

Technicky jsou tyto periferie připojené přes oddělovací obvody, které se postarají, aby na výstupech byla správná data, nebo naopak aby ta vstupní šla do systému pouze tehdy, když si o ně procesor řekne.

V roli takového nejjednoduššího obvodu si můžeme představit třeba osmici klopných obvodů typu D, například 74HCT377\. Tento obvod obsahuje osm registrů D se společným hodinovým vstupem CP a společným povolovacím vstupem /E. Pokud je /E neaktivní (=1), zůstává obvod stále ve stejném stavu a na výstupech udržuje předchozí zapsanou hodnotu. Pokud je /E aktivní (=0), tak náběžná hrana na hodinovém vstupu CP zapíše data ze vstupů D0-D7 do vnitřních klopných registrů. Odtamtud se pak objeví na výstupech.

![359-1.png](images/000011.png)