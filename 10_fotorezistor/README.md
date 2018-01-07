# 10 Fotorezistor {#10-fotorezistor}

Už jsme si ukázali svítící diody, tedy součástky, které mění elektrický proud na světlo. Nastal čas podívat se na součástku s opačnou funkcí, tedy takovou, která reaguje na světlo. Už vás asi nepřekvapí, že takových je celá řada. Já začnu tou nejjednodušší, fotorezistorem.

![116-1.jpeg](images/00222.jpeg)

Jak název napovídá, půjde o nějaké spojení světla a rezistoru. Fotorezistor funguje velmi podobně jako rezistor, jen s tím rozdílem, že se jeho odpor mění podle toho, kolik světla na něj dopadá. Čím víc světla, tím nižší odpor.

Všimněte si, že fotorezistor má průhledný kryt – logicky, protože musí propouštět světlo – pod kterým je vidět struktura, připomínající vlnovku. Ta je tvořena polovodičem. Světlo, dopadající na polovodič, zvyšuje množství volných elektronů, které tak mohou sloužit jako přenosové médium. Větší množství světla znamená víc volných elektronů, a tedy vyšší vodivost.

U fotorezistorů se udává nejčastěji odpor při osvětlení 10 luxů a teplotě 25 °C (označuje se R10lx) a u těch nejčastějších a nejlevnějších, kterých koupíte za pětikorunu celý sáček, to bývá okolo 10 kΩ. Bez dalších znalostí, například přesného typu nebo kalibrace, se moc nehodí na přesné měření osvitu, ale to ve spoustě aplikací nevadí. Třeba pro automatické spínání osvětlení nebývá potřeba přesně stanovit, že se má spustit při 28 luxech a vypnout při 37 luxech. Stejně tak například u optických závor (zařízení, které reaguje na přerušení paprsku) nám stačí vědět, jestli světlo dopadá, nebo nedopadá (a tedy jestli je odpor nízký / vysoký).

Pojďte si to zkusit, jestli to funguje tak, jak si představujete. Co když zapojíte takový fotorezistor místo obyčejného rezistoru do série s LED?

![117-1.png](images/000236.png)

LED bude svítit, ovšem když zastíníte fotorezistor prstem, její jas se sníží!