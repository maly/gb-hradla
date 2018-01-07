## 9.4 Krok zpět k drátům {#9-4-krok-zp-t-k-dr-t-m}

Připravte si zase nepájivá kontaktní pole. Připravte si propojovací vodiče. Tentokrát odpojte napájení, vezmete si potřebné napětí přímo z Arduina. Všimněte si na Arduinu dole dvou vývodů, označených GND (ten je zdvojený) a 5 V. GND je i v horní řadě vývodů – je úplně jedno, který použijete, protože uvnitř jsou stejně propojené. A teď připojte tyto dva vývody k napájecím lištám na kontaktním poli. Nějak takto:

![111-2.png](images/000130.png)

Tak, a teď pokaždé, když Arduino poběží, budete mít na kontaktním poli i potřebné napájecí napětí. Jupí.

Zapojte si LED.

Z minulé kapitoly si jistě pamatujete, že LED má dva vývody a zapojuje se k ní rezistor. Udělejte to podle obrázku:

![112-1.png](images/000163.png)

Připojte Arduino k počítači – ani v něm nemusí být nic nahraného. LED by měla svítit. Pokud nesvítí, otočte ji (a tím otočením myslím, že prohodíte její vývody, ne že ji třeba… co já vím… vzhůru nohama, nebo tak něco).

Svítí? Jupí. Teď ji propojte s Arduinem:

![112-2.png](images/000176.png)

Všimněte si, co přesně jsem nakreslil – vodič, který propojoval LED a kladný pól, jsem odstranil, a místo kladného pólu jsem daný vývod LED zapojil do Arduina, na pin číslo 8\. Proč? No protože jsem se rozhodl, že budu LED ovládat Arduinem. A vy taky!

Máte stále otevřený ten příklad Blink? Tak prosím všude, kde je LED_BUILTIN, napište 8\. Jako že osmičku. Je to na třech místech. Výsledek bude vypadat nějak takhle:

<pre class="kod">// the setup function runs once when you press reset or power the board</pre>

<pre class="kod">void setup() {</pre>

<pre class="kod">    // initialize digital pin LED_BUILTIN as an output.</pre>

<pre class="kod">    pinMode(8, OUTPUT);</pre>

}  

<pre class="kod">// the loop function runs over and over again forever</pre>

<pre class="kod">void loop() {</pre>

<pre class="kod">    digitalWrite(8, HIGH);   // turn the LED on (HIGH is the voltage level)</pre>

<pre class="kod">    delay(1000);             // wait for a second</pre>

<pre class="kod">    digitalWrite(8, LOW);    // turn the LED off by making the voltage LOW</pre>

<pre class="kod">    delay(1000);             // wait for a second</pre>

<pre class="kod">}</pre>

Teď přeložte a nahrajte. Pokud vše půjde bez problémů, stane se co? Správně, bude blikat ta naše LED!

Ptáte se, proč právě osmičku? Všimněte si, že v té delší řadě vývodů jsou vývody očíslované od 0 do 13\. Je tu tedy 14 vývodů – pinů, k nimž můžeme připojit téměř cokoli. V praxi se moc nepoužívají vývody 0 a 1, protože přes ně Arduino komunikuje se světem, ale ten zbytek je volný. A já jsem LED připojil do vývodu číslo 8\. Co kdybych ji zapojil do vývodu číslo 9, co by se stalo?

Neptejte se mě, zkuste si to – přepojte vodič z osmičky na devítku, uvidíte sami. Možná bude potřeba ještě něco v programu změnit… ne?

Máte?

Dobře, a teď si zapojte dvě LEDky. Úplně stejné zapojení, druhá LED taky potřebuje rezistor, tak na to nezapomeňte, no a jednu LED připojte k Arduinu na výstup 8, druhou na výstup 9, a zkuste si, aby blikaly na střídačku.

Máte i toto?

Právě jste vytvořili svůj první programovatelný číslicový obvod! Jaký to je pocit?

_(Chvilka na opájení se vlastní šikovností…)_

Pojďme teď – nebo ne, ještě chvilku se chvalte, jak jste šikovní! Zasloužíte si to!

_(Ještě krátká chvilka!)_

A teď dojde na lámání chleba. _Hello world_ už máme, tak teď následují ty protivné prozaické otázky: Proč to svítí? Proč to obráceně nesvítí? Co je to těch 5 voltů? Proč zrovna pět? A jak je možné, že já tady napíšu nějaká písmena, z toho se stane nějaký kód, a ten se nějak nahraje do té součástky? A jak se tam jako nahraje? Kam se tam nahraje? A jak ta součástka pozná, že má zrovna blikat LEDkou?

Ale ještě, než si to řekneme, zkuste si cvičení pro bystré hlavy: Zapojte dvě LED na jeden vývod Arduina tak, aby při stavu HIGH svítila jedna, a při stavu LOW svítila druhá! Napadá vás, jak to udělat?