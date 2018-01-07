## 6.4 Transformátor {#6-4-transform-tor}

Transformátor je známá součástka, se kterou máme všichni každodenní zkušenost. Transformátor slouží k tomu, abychom určitou úroveň napětí – třeba 230 voltů v zásuvce – snížili na nižší hodnotu, nebo naopak na vyšší. Transformátor je fyzicky tvořen dvěma cívkami na společném jádru. Změna proudu v jedné z těchto cívek vyvolá změnu magnetického pole, a tato změna v druhé cívce vyvolá indukci proudu. Poměr počtu závitů obou cívek udává poměr, v němž se transformuje proud, a tedy i napětí. Pokud transformujeme napětí 230 V přes transformátor s poměrem závitů např. 1000:10000, získáme napětí 23 voltů, tedy desetinové, ovšem procházející proud bude desetinásobný.

![114-1.jpeg](images/00192.jpeg)

Toho se využívá například při indukčním ohřevu – pod indukční deskou je cívka s mnoha závity, druhou cívku tvoří dno hrnce – které můžeme považovat za jeden závit. V něm se indukcí vytváří velmi nízké napětí, ovšem prochází jím obrovský proud, který ohřívá vodič – v našem případě dno.

### 6.4.1 DC měnič {#6-4-1-dc-m-ni}

Transformátor dokáže velmi efektivně měnit úroveň napětí, ale pouze tehdy, pokud na něj připojíme střídavé napětí. Stejnosměrné napětí transformátorem neprochází, protože nevyvolává změny magnetického pole. Pokud potřebujete změnit stejnosměrné napětí na jiné (třeba 5 voltů na 3,3, nebo na 12), použijte takzvané DC měniče (DC converters), což jsou zapojení, které buď pomocí kondenzátoru (nábojová pumpa – charge pump) nebo cívky (spínaný zdroj – switched-mode power supply) dokáží přeměnit stejnosměrné napětí na jiné. Buď na vyšší (a pak se jim říká step-up nebo boost convertor), nebo na nižší (step-down, popřípadě buck convertor).

[eknh.cz/cpump](https://eknh.cz/cpump)

### 6.4.2 Stabilizátor {#6-4-2-stabiliz-tor}

Pokud potřebujeme přesnou velikost napětí – a to v číslicové technice potřebujeme vždy! – musíme napětí, které přivádíme do obvodu, stabilizovat. V praxi se postupuje tak, že pomocí transformátoru snížíme síťové napětí 230 V střídavého proudu na nižší hodnotu, ovšem o něco vyšší, než je požadované. Například na 10 voltů. Toto napětí usměrníme pomocí diod, což jej opět o něco sníží, a výsledné stejnosměrné napětí filtrujeme pomocí kondenzátorů. Máme na výstupu například 8 voltů, a musíme použít ještě speciální součástku, zvanou stabilizátor, která dokáže udržet předem danou hodnotu napětí. Nejčastější typ stabilizátoru je takový, který přebytečné napětí „spálí“ – promění jej v teplo. Proto takové zdroje intenzivně hřejí a potřebují chlazení. Pro náročnější zařízení se používají stabilizátory s nízkým úbytkem, kterým stačí na vstupu napětí třeba jen o jeden volt vyšší než je požadované, a tím pracují efektivněji a nemají tak velké ztráty.

V napájecích obvodech u PC se používá kombinace transformátoru a spínaného zdroje. Dobré na této kombinaci je, že má relativně malé ztráty a vysokou efektivitu, a že dokáže dát velké a stabilní proudy ve stabilních úrovních napětí. Nevýhodou je, že potřebují stálý minimální odběr, a pokud je zapojíme „naprázdno“, tak během několika sekund shoří, protože v jejich cívkách budou vznikat velké proudy, které nebudou mít kam odejít...

### 6.4.3 7805 {#6-4-3-7805}

Označení 7805 nese součástka, kterou vyráběla už Tesla za socialismu. Jde o napěťový stabilizátor, který dokáže snížit napětí v rozsahu 7,5 V – 35 V na napětí 5 voltů. Jeho zapojení je velmi jednoduché: je to součástka se třemi vývody. Prostřední je společná zem, a dva krajní jsou vstup a výstup. Zapojuje se spolu se dvěma kondenzátory:

![115-1_.png](images/000205.png)![115-2.png](images/000216.png)

Někde se setkáte i s doporučením použít elektrolytické kondenzátory s řádově vyšší kapacitou, třeba i 10 µF. To může pomoci s vykrýváním odběrových špiček, ale zase má zdroj pomalejší náběh.

Takto zapojený stabilizátor dá dostatek proudu pro napájení číslicového obvodu. Pokud je potřeba větší proud, počítejte s tím, že se stabilizátor bude zahřívat, a přidejte k němu chladič. Chladič je tvarovaný hliníkový profil, který má velkou plochu a odvádí dobře teplo. Uprostřed je otvor pro šroub, stejný, jako má obvod 7805.

![116-1_.jpeg](images/00230.jpeg)

Obvod 7805 je levný, dobře dostupný a jednoduchý k použití. Bohužel má i své nevýhody, především vysokou vlastní spotřebu (ale k tomu se ještě dostaneme v kapitole o nízkopříkonových zařízeních). Pro stabilizaci napětí z baterií proto není příliš vhodný, ale pro zapojení, poháněné transformátorem (třeba starým napájecím adaptérem pro mobilní telefony nebo notebooky), jde o řešení použitelné.

##### 7 Polovodiče {#7-polovodi-e}