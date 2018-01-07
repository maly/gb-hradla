## 18.2 Blikač {#18-2-blika}

![208-1.png](images/000379.png)

Vzpomínáte si na blikač z první kapitoly? Jak ten vypadal?

Co se tu děje? Na vstupu 1, úplně vlevo, je po zapnutí dejme tomu logická 0\. Na výstupu 2 je tedy logická 1, ta je i na vstupu 3\. Na výstupu 4 je zase logická 0, no a invertor IC1C z ní dělá logickou 1 na výstupu celého zapojení. Důvod, proč je tu použitý vlastně na první pohled „zbytečný“ invertor, je ten, že kondenzátor C1 by se mohl nabíjet či vybíjet přes obvody, co jsou zapojené na výstup – tady třeba přes LED. Tím, že zařadíte další invertor, vlastně oddělíte vnitřní logiku blikače od ovládaných součástek.

Značení IC1A, IC1B atd. napovídá, že se jedná stále o jeden integrovaný obvod, konkrétně číslo 1, a v něm používáme hradla A, B, C. IC je z anglického Integrated Circuit. Někdy se v českých schématech setkáte s označením IO („integrovaný obvod“), zahraniční časopisy občas používají „U“ („unit“)…

Rezistor přenáší napětí z výstupu 2 – tam je logická 1 – zpátky na vstup. V předchozím zapojení, bez kondenzátoru, by se invertor IC1A rovnou přepnul. Jenže tady část proudu sebere kondenzátor. Bude se pomalu nabíjet, napětí poroste, a v určitém okamžiku překročí rozhodovací hranici. V tu chvíli IC1A přepne, na výstupu bude 0, na výstupu druhého invertoru tedy jednička, na výstupu třetího nula.

A celý proces pojede obráceně. Teď se bude naopak kondenzátor vybíjet. A jakmile napětí klesne pod danou mez, zase se celý obvod přepne. Průběh napětí na vstupu 1 bude vypadat nějak takto:

![209-1.png](images/000255.png)

Teď už vám je jasné, že mnohem lepší a čistší by bylo použít invertory, které mají na vstupech Schmittův obvod, tedy typ 7414.

Samozřejmě, že toto není jediný typ astabilního obvodu. Existují i další zapojení:

![209-2.png](images/000392.png)

Frekvence kmitání takovýchto oscilátorů je zhruba 1 / (2,2.R.C) (Hz; Ω, F)

Existují i „oscilátory chudého muže“ s jedním invertorem:

![210-1.png](images/000367.png)

nebo s dvěma kondenzátory

![210-2.png](images/000409.png)

Ovšem v praxi se používá buď přesnější časovač 555 (NE555), nebo krystalový oscilátor, kde je kondenzátor nahrazen součástkou, zvanou „krystal“, což je opravdu kousek křemíkového krystalu, který mění svou kapacitu s určitou frekvencí, která je velmi přesná a stabilní.

![211-1.png](images/000035.png)

Krystalové oscilátory se používají všude tam, kde je potřeba mít přesný zdroj pulsů.