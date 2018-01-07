## 18.8 Hodiny {#18-8-hodiny}

Když píšu „hodiny“, nepředstavujte si prosím nic sofistikovaného, natož švýcarského natahovacího se strojkem. Je to prostě jen jeden vodič, na kterém se plus mínus pravidelně střídají 0 a 1\. Tento signál podobně jako srdeční tep řídí pak celý obvod. V zásadě má funkci takovou, že říká, kdy nějaký obvod smí změnit svůj stav. A protože u většiny zapojení bývá opravdu pravidelný a přesný a určuje rytmus vnitřních dějů, říká se mu „hodinový puls„.

Výchozí stav je takový, že vstup E je 0\. Výstupy zůstávají stále ve stejné úrovni. Jakmile je E = 1, nastaví se výstupy podle vstupu D. Pokud je nula, bude Q = 0 a /Q = 1, pokud je jedna, bude Q = 1 a /Q = 0\. Dokud bude E = 1, budou výstupy reagovat na vstup D. Jakmile přepneme vstup E zpátky na 0, zůstane obvod v posledním nastaveném stavu. Proto ten český název „závora“ – jakmile _spadne_, zůstane výsledek _zamknutý_ až do doby, než se opět zvedne.

Modifikací tohoto obvodu dostaneme zapojení, které se přepíná pouze v jednom jediném okamžiku, totiž když se mění stav hodinového vstupu. Nejčastěji reaguje na změnu z 0 do 1 – tomu okamžiku se říká _náběžná hrana hodinového pulsu_.

Výsledek se nazývá „klopný obvod D“. Můžeme si to představit jako paměťovou buňku pro jeden bit informace. Přivedeme tento bit na vstup D (buď 1, nebo 0), a „zapamatujeme“ si jej tak, že na vstup Clock přivedeme krátký impuls. Impulsem je míněn přechod z 0 do 1 a opět zpátky na  0\. Nějak takto:

![223-2.png](../images/000092.png)

Zapamatovaná hodnota je na výstupu Q, na výstupu /Q (NOT Q) je jeho negovaná hodnota.
