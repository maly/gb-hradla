## 30.3 Stavíme z polotovarů {#30-3-stav-me-z-polotovar}

To byl takový morální apel, a teď se vraťme k meteostanici.

DHT22 i BMP180 jsou součástky, které jsou dostatečně popsané, zdokumentované, je k nim dostatek knihoven… Vy obvykle začínejte prosím s tím, že si zkusíte připojit jednu z nich, podívat se na příklady, vyzkoušíte, že vám to funguje, popřípadě proč ne, pak totéž s druhou…

Teď si to zkusme ale jinak. Třeba s tím barometrem BMP180\. Když se na modul s touto součástkou podíváte, najdete většinou čtyři vývody: Vcc, GND, SDA a SCL. Co to znamená?

Vcc a GND je jasné, to je napájení. SCL a SDA napovídá, že se bude zařízení připojovat přes sběrnici I2C. Najděte si datasheet pro BMP180 a ověřte si, že to je opravdu tak.

V datasheetu si všimněte, že napájecí napětí je 3,3 voltů. To by mohl být problém – jenže naštěstí moduly s BMP180 obsahují stabilizátor napětí – je to ta miniaturní černá součástka se třemi vývody:

![344-1.jpeg](images/00398.jpeg)

Letmým googlením najdete i schéma takového modulu:

![344-2.jpeg](images/00383.jpeg)

Vidíte, že je tam stabilizátor, který sníží napájecí napětí 5 V z Arduina na požadované 3,3 V. Pak vidíte, že jsou použité i pull-up rezistory na 3,3 V pro sběrnici I2C. Budeme ji moci připojit k Arduinu, když víme, že to používá 5 V?

No, vzpomeňte si na popis sběrnice I2C: logická 0 je zajištěná tím, že zařízení připojují jednotlivé linky k zemi, logická 1 je zajištěná právě pomocí pull-up rezistorů. Taky víte, že 3,3 V je dostatečné napětí pro logickou 1 i pro zařízení, pracující s pěti volty, takže v tomto ohledu je to bezpečné. Může se tam někudy dostat + 5 voltů? Teoreticky ano, pokud bude na téže sběrnici připojené zařízení s pull-upy na + 5 V, nebo pokud budou zapojené interní pull-upy. Jinak ne.

V datasheetu je dále popsána přesně funkce celého obvodu – jak se adresuje, kde jsou jaké informace, jak se zadávají kalibrační údaje a spousta dalších věcí. A to je přesně okamžik, kde vám doporučím nevynalézat kolo a použít hotovou knihovnu. Vhodné jsou knihovny od výrobců takových modulů – nejčastěji Sparkfun nebo Adafruit.

Pokud najdete knihovnu BMP085, nebojte se – to je starší verze téhož, a v popisu většinou najdete, že umí i BMP180

Součástí těchto knihoven bývá i příklad měření. Podívejte se do něj – zjistíte, že se tam pracuje s aktuální nadmořskou výškou – tedy s tou vaší. Proč? No protože změřený tlak je ten reálný, co je okolo vás, ale aby se tlaky snáze porovnávaly, přepočítávají se na hladinu moře. Přepočet je jednoduchý – počítá se, že na každý metr nadmořské výšky připadá pokles tlaku o 8 Pa (jen pro jistotu: standardní tlak 1013,25 hPa = 101,325 kPa = 101325 Pa).

Například knihovna Adafruit BMP085 Library obsahuje ukázku kódu:

<pre class="kod">#include &lt;Wire.h&gt;</pre>

<pre class="kod">#include &lt;Adafruit_BMP085.h&gt;</pre>

<pre class="kod">Adafruit_BMP085 bmp; </pre>

<pre class="kod">void setup() {</pre>

<pre class="kod">    Serial.begin(9600);</pre>

<pre class="kod">    if (!bmp.begin()) {</pre>

<pre class="kod">        Serial.println(„Could not find a valid BMP085 sensor, check wiring!“);</pre>

<pre class="kod">        while (1) {}</pre>

<pre class="kod">    }</pre>

}  

<pre class="kod">void loop() {</pre>

<pre class="kod">    Serial.print(„Temperature = “);</pre>

<pre class="kod">    Serial.print(bmp.readTemperature());</pre>

<pre class="kod">    Serial.println(„ *C“);</pre>

<pre class="kod">    Serial.print(„Pressure = “);</pre>

<pre class="kod">    Serial.print(bmp.readPressure());</pre>

<pre class="kod">    Serial.println(„ Pa“);</pre>

<pre class="kod">    delay(500);</pre>

<pre class="kod">}</pre>

V příkladu není použitý přepočet na hladinu moře, proto se nedivte, když výsledky budou výrazně nižší, než očekáváte. Můžete si výsledek přepočítat pomocí výše uvedeného vzorce, nebo použít funkci bmp.readSealevelPressure(altitude), kde altitude je nadmořská výška v metrech.

Kde zjistit svou nadmořskou výšku? Můžete použít třeba GPS, ale nejjednodušší způsob je ten, že se podíváte na mapu, tam bude u vaší pozice uvedena i nadmořská výška! Nebo zkuste [api.mapy.cz/view?page=altitude](https://api.mapy.cz/view?page=altitude)

Senzor dokáže změřit i nadmořskou výšku. Chcete vědět, jak to dělá? No, změří tlak, a předpokládá, že na hladině moře je standardních 101325 Pa. Což bývá málokdy, protože tlak se mění s počasím, rozdíl může být třeba 3 kPa během několika dní, a takový rozdíl představuje přes 350 metrů výškového rozdílu.

U pevné meteostanice bude lepší nastavit výšku odečtem z mapy natvrdo do kódu.

Druhý polotovar, DHT11 nebo DHT22, je nejjednodušší připojit podle standardního zapojení a využít hotovou knihovnu. Když se podíváte do datasheetů, zjistíte, že komunikace s těmito senzory není úplně jednoduchá, a pokud se vám zrovna nechce znovuvynalézat druhé kolo (a komu by se chtělo, když může ušetřený čas věnovat něčemu zajímavějšímu, než je opakování cizích chyb?), použijte ji.

![346-1.png](images/000214.png)

Možné zapojení celé meteostanice ukazuje obrázek. Obvod DHT je připojen podle příkladu z knihovny DHT Simple na pin 2, snímač BMP180 je zapojen na sběrnici I2C. U DHT11 je zapojený i pull-up rezistor 10k.

Když oba příklady spojíme do jednoho, získáme tak kód, který bude vypisovat tlak, vlhkost a dvě různé teploty (jedna je z BMP180, jedna z DHT11). Můžete si vybrat, které budete spíš věřit, nebo je prostě zprůměrovat (anebo použít samostatný teploměr).

Mimochodem, měření teploty není tak triviální, jak vypadá. Teplotu ovlivňuje spousta věcí – například nezapomínejme, že součástky také „topí“. U Arduina to není tak extrémní, ale třeba ESP8266, o němž se ještě budeme bavit, dokáže velmi pěkně ohřívat okolí, i o několik stupňů. Teploměr by samozřejmě neměl být na přímém slunci, měl by být daleko od ploch, které mohou sálat, měl by okolo něho proudit volně vzduch, …

No a když máte data, co s nimi? Zatím si je můžete zpracovat v počítači, nebo je můžete ukládat na SD kartu (o tom jsme se už bavili…) Později si tohle celé vylepšíme o posílání dat na server…

Schéma a zdrojový kód najdete na [eknh.cz/meteo](https://eknh.cz/meteo)

##### 31 Bezdrátový přenos dat {#31-bezdr-tov-p-enos-dat}