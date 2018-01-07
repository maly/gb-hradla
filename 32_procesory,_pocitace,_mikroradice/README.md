# 32 Procesory, počítače, mikrořadiče {#32-procesory-po-ta-e-mikro-adi-e}

Od hradel jsme prošli přes kombinační obvody a klopné obvody až k čítačům, registrům a pamětem. Teď se dostáváme k poslední velké oblasti číslicové techniky, k procesorům a počítačům.

Po zkušenosti z předchozích kapitol už jistě tušíte, že ani procesory nebudou nic mystického a tajuplného. A ono taky ne – jde jen o kombinaci toho, co už známe. Nevěříte? To byste měli. Existují totiž lidé, kteří si opravdu postavili svůj procesor z těch integrovaných obvodů, s nimiž jsme se seznámili. Ostatně, před vznikem mikroprocesoru ani jiná cesta nebyla.

Co to je vlastně procesor? Obecně jde o součást systému, která umí několik věcí:

1. Přečte z připojené paměti nějakou binární hodnotu.

2. Podle této binární hodnoty vykoná instrukci, která spočívá buď v přesunu dat odněkud někam, nebo v jejich zpracování v aritmeticko-logické jednotce.

3. Posune se k další adrese v paměti programu.

4. Řídí provádění těchto instrukcí a ovládá připojená zařízení.

K tomu potřebuje několik základních částí:

• Aritmeticko-logická jednotka (ALU). S ní jsme se už seznámili v kapitole o kombinační logice.

• Registry pro udržení dat, s nimiž se pracuje. Asi vás nepřekvapí, že jde o naše staré dobré známé klopné obvody D.

• Čítač instrukcí (PC – Program Counter). Technicky jde opravdu o jeden mnohabitový čítač s možností nulování a přednastavení hodnoty, tedy něco podobného, jako umí obvody 74193.

• Dekodér instrukcí. To je zase jen kombinační obvod, který podle kódu instrukce aktivuje požadované součásti v požadovaném pořadí.

Procesory se původně stavěly z mnoha desek, plných tranzistorů, později z méně desek, plných integrovaných obvodů, později, jak se technologie zlepšovala, klesal počet nutných integrovaných obvodů, až počátkem 70\. let 20\. století pokročila technika natolik, že umožnila naprostou většinu funkce procesoru integrovat do jednoho nebo do několika málo pouzder. Zrodil se mikroprocesor.

Za úplně první mikroprocesor je považován obvod 4004 firmy Intel. Byl vyvinut pro kalkulátory. Brzy po něm přišla rozšířená verze 8008, a po něm první úspěšný mikroprocesor Intel 8080\. U něj se zastavíme podrobněji. Jednak proto, že z něj se postupnou evolucí vyvinuly šestnáctibitové procesory řady 80 × 86 (a z nich pak Pentia a Core a další dodneška používané mikroprocesory), jednak proto, že se na něm dají dobře ukázat základní principy funkce těchto obvodů, a v neposlední řadě i proto, že v osmdesátých letech byl tento procesor používaný ve většině tehdejších československých mikropočítačů (protože jeho klon vyráběla československá TESLA pod označením MHB8080A).