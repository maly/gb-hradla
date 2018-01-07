## 10.4 Fotorezistor a Arduino {#10-4-fotorezistor-a-arduino}

Jeden z nejčastěji připojovaných senzorů k Arduinu je právě fotorezistor. Je levný, jednoduchý na obsluhu, tak co by ne, že?

Pro takovéhle typy snímačů, které nemají digitální výstup (třeba jako tlačítko), ale (nejčastěji) mění svůj odpor, má Arduino speciální vstupy – analogové A0 až A5\. Funkce analogRead() dokáže zjistit, jaké napětí je na tomto vstupu, a převést ho na škálu hodnot 0 až 1023.

Nula samozřejmě znamená, že daný vstup má úroveň země. Ale kolik je maximum, tedy těch 1023?

To je správná otázka. Odpověď zní: 1023 je hodnota, která je naměřená tehdy, když je na analogovém vstupu takzvané referenční napětí!

Odpověď jak od chytré horákyně, že? A kolik je tedy to referenční napětí?

Většinou, pokud není určeno jinak, to je napájecí napětí, tedy zhruba 5 voltů. Zhruba píšu proto, že toto napětí může kolísat, a u některých typů Arduin může být třeba 3,3 voltů. U Arduina UNO ale bude zhruba těch 5 voltů.

Můžete ale použít vnitřní zdroj referenčního napětí 1,1 voltu.

No a konečně můžete říct, že si referenční napětí, ne vyšší než 5 V, vytvoříte nějak sami a přivedete ho na vstup AREF. Jak si ho vytvoříte? Buď nějakým stabilizátorem, nebo specializovanou součástkou – generátorem referenčního napětí. Dělají se například přesné generátory 1,023 voltu – pak naměřená hodnota odpovídá velmi přesně milivoltům.

Ale to jsem trochu odbočil. Pokud k Arduinu připojujete třeba fotorezistor nebo podobnou součástku (například termistor, což je rezistor, jehož odpor je závislý na teplotě), používá se většinou některý z analogových vstupů, a součástku zapojujete v sérii s rezistorem, jako napěťový dělič. Analogový vstup totiž měří _napětí_, nikoli _proud_. Kdybyste zapojili třeba jen fotorezistor na + 5 voltů, tak by se se změnou odporu měnil proud, ale napětí by bylo stále 5 voltů.

![122-1.png](images/000277.png)

Když si fotorezistor takto zapojíte, zjistíte, že při velmi silném osvětlení funkce analogRead(A0) vrátí téměř 1023, ve tmě klesne – nikoli na nulu, protože odpor fotorezistoru nebude nekonečný, takže napětí neklesne k ideální nule, ale klesne hodně nízko.

<pre class="kod">void setup () {</pre>

<pre class="kod">    Serial.begin(9600);</pre>

<pre class="kod">}</pre>

<pre class="kod">void loop() {</pre>

<pre class="kod">    int a = analogRead(A0);</pre>

<pre class="kod">    Serial.println(a);</pre>

<pre class="kod">}</pre>

Když tento program napíšete do Arduino IDE a nahrajete do Arduina, bude měřit napětí na vstupu A0 a vypisovat ho na sériovou konzoli. Sériová konzole je způsob, jakým Arduino může posílat údaje do připojeného počítače. Princip popíšu později, teď stačí, abyste věděli, že v Arduino IDE je v menu Nástroje (Tools) položka Sériový monitor (Serial Monitor). Když ji vyberete, otevře se nové okno, a v něm se vypisuje to, co Arduino pošle funkcí Serial.println().

Všimněte si, že ve funkci Setup volám Serial.begin(9600). Tato funkce zajistí zapnutí této komunikace a nastavení přenosové rychlosti. Toto číslo je velmi důležité – přenosová rychlost, s jakou Arduino pracuje, musí být shodná s přenosovou rychlostí, jakou komunikuje počítač.

![123-1.jpeg](images/00288.jpeg)

Ta se nastavuje v Sériovém monitoru vpravo dole – všimněte si hodnoty „9600 baudů“.

Postavte si teď přesně takový detektor tmy, jako předtím, ale tentokrát s Arduinem. Vlastně moment – vy jste si ho už postavili, to na předchozím obrázku, to je přesně on! Použijete LED, která je v Arduinu zapojena na výstupu 13, a máte to! Teď stačí v nekonečné smyčce loop() opakovat stále dokola totéž: Přečíst analogový stav na vstupu A0, a podle načtené hodnoty LED buď rozsvítit, nebo zhasnout. Buď metodou pokus-omyl, nebo vypsáním naměřených hodnot zjistíte, která hodnota je pro vás už „dostatečná tma“, a pokud načtete víc, LED zhasnete, pokud míň, LED rozsvítíte. Takhle jednoduché to bude.

Když použijete EduShield, tak nemusíte ani nic zapojovat. EduShield má totiž na sobě fotorezistor zapojený přesně tak, jak jsem právě popsal.

##### 11 Termistor {#11-termistor}