# 25 Sériová paměť prakticky {#25-s-riov-pam-prakticky}

Pojďme si připojit sériovou paměť a _něco_ s ní dělat. Co? Pojďme si třeba ukládat naměřená data do sériové paměti EEPROM, připojené přes sběrnici I2C.

Arduino Uno má samozřejmě vyvedené signály SDA a SCL pro sběrnici I2C. Překladač pro Arduino navíc nabízí knihovnu Wire, která právě se sběrnicí I2C pracuje. Navíc umí zapnout interní pull-up rezistory, takže není potřeba připojovat ehterní. Připojení sériové paměti je tak otázka jen několika propojovacích vodičů.

Použijte paměť z řady 24LC – třeba 24LC01, ale klidně i jakoukoli jinou s větší kapacitou. Budeme si ukazovat princip, ne konkrétní řešení.

Paměti 24LCxx mají následující zapojení vývodů:

![310-1.png](../images/000275.png)

Vývody 1, 2 a 3 nastavují adresu. Už jsem se zmiňoval, že zařízení na sběrnici I2C mají svou sedmibitovou adresu, a že u některých ji lze změnit. Sériové paměti EEPROM mívají jako základní adresu 0x50, a tři nejnižší bity lze nastavit pomocí vstupů A0-A2\. Konkrétní čip tedy může být nastaven tak, aby se hlásil na jedné ze sedmi adres 0x50 – 0x57\. Pokud máte na jedné sběrnici jen jednu paměť, tak připojte všechny vstupy A na zem, paměť tak bude mít adresu 0x50.

Na zem připojte i vývod 7 – WP (Write protect). Pokud je připojen k zemi, může se do paměti zapisovat, pokud je spojen s napájecím napětím, je zápis zakázán.

Teď zbývá jen připojit napájecí napětí a signály pro I2C, tedy SDA a SCL. Na konci knihy, v přílohách, najdete takzvaný „pinout“, neboli rozložení vývodů Arduina včetně speciálních funkcí. A tam zjistíte, že SCL je vyveden na pin A5 a SDA na pin A4\. propojení pak vypadá nějak takto:

![311-1.png](../images/000036.png)

Pro zápis do této paměti stačí poslat po sběrnici I2C nejprve adresu obvodu (tedy výše zmíněných 0x50), poté adresu v paměti (dva bajty, nejprve vyšší), a nakonec požadovaný bajt k zápisu. Nezapomeňte po zápisu počkat dostatečně dlouhou dobu – EEPROM zapisují pomalu.

<pre class="kod">void writeEEPROM(unsigned int address, uint8_t data) </pre>

<pre class="kod">{</pre>

<pre class="kod">    Wire.beginTransmission(0x50);</pre>

<pre class="kod">    Wire.send((int)(address &gt;&gt; 8)); // MSB</pre>

<pre class="kod">    Wire.send((int)(address &amp; 0xFF)); // LSB</pre>

<pre class="kod">    Wire.send(data);</pre>

<pre class="kod">    Wire.endTransmission();</pre>

<pre class="kod">    delay(5);</pre>

<pre class="kod">}</pre>

Při čtení pošlete adresu stejně jako při zápisu, ale pak namísto poslání bajtu k zápisu jeden bajt přečtěte:

<pre class="kod">uint8_t readEEPROM(unsigned int address) </pre>

<pre class="kod">{</pre>

<pre class="kod">    uint8_t data = 0xFF;</pre>

<pre class="kod">    Wire.beginTransmission(0x50);</pre>

<pre class="kod">    Wire.send((int)(address &gt;&gt; 8));   // MSB</pre>

<pre class="kod">    Wire.send((int)(address &amp; 0xFF)); // LSB</pre>

<pre class="kod">    Wire.endTransmission();</pre>

<pre class="kod">    Wire.requestFrom(0x50,1);</pre>

<pre class="kod">    if (Wire.available()) data = Wire.receive();</pre>

<pre class="kod">    return data;</pre>

<pre class="kod">}</pre>

Schéma a zdrojový kód najdete na [eknh.cz/eep](https://eknh.cz/eep)

##### 26 Hodiny reálného času {#26-hodiny-re-ln-ho-asu}
