## 2.3 LED podrobněji {#2-3-led-podrobn-ji}

Nejjednodušší způsob, jak to udělat, je použít LED. LED je součástka, která za určitých podmínek mění procházející elektrický proud na světlo. Nejčastější typ LED vypadá jako takový malý klobouček s dvěma vývody.

![056-1.jpeg](images/00107.jpeg)

Všimněte si několika věcí:

• Jeden vývod je delší (pokud si ho nezkrátíte…).

• Uvnitř diody je větší část s takovou miniaturní mističkou (už jsem říkal, že se vám bude hodit lupa?) a menší část. Větší část má kratší vývod, menší část delší (asi aby to bylo spravedlivé).

• Na spodním okraji kloboučku je zvýrazněná hrana, a ta je v jednom místě seříznutá. Je to u té větší části s kratším vývodem.

Dioda je součástka, která má dva vývody, a protože se bavíme jako elektronici, tak si budeme pamatovat, že vývody jsou připojené k elektrodám, které se jmenují _katoda_ (což je záporná elektroda) a _anoda_ (to je kladná elektroda – mnemotechnická pomůcka: _kladná_ elektroda tam má to _ano_, a ti, co umí rusky, vědí, že _da_ znamená _ano_). Seříznutá hrana označuje _katodu_. Katoda je ten větší útvar uvnitř diody. Ten druhý vývod, bez seříznuté hrany a s menším útvarem, to je kladná elektroda, anoda. (_Další mnemotechnická pomůcka: delší vývod si můžete zkrátit a ten ucvaknutý kousek přeložit napříč, abyste získali „+“_)

![056-2.jpeg](images/00110.jpeg)

Zapojte anodu na výstup číslo 6 integrovaného obvodu. Asi není dobrý nápad ji strkat přímo na místo. Dejte si ji kousek stranou, do jiné řady vývodů, a anodu propojte s vývodem 6 nějakým vodičem.

Předposlední krok: Katodu připojte přes rezistor s odporem 330 ohmů (rozpoznávání hodnot viz předchozí text) na zápornou napájecí lištu. Pamatujte si: LED vždy s rezistorem! Jinak ji spálíte.

Teď připojte zdroj k nepájivému kontaktnímu poli. Modrou – zápornou – napájecí lištu na záporný pól (budeme mu říkat zem, proč, to si řekneme později), červenou na kladný (+ 5 V). Můžete si zdroj ještě proměřit na multimetru: nastavte rozsah 20 V, černou sondu připojte na zem (tedy na zápornou, modrou lištu), červenou na + 5 V, a pokud se na displeji ukáže něco okolo 5, je to v pořádku. Pokud se ukáže záporné číslo, máte prohozené plus a mínus.

Nezapomeňte propojit horní napájecí lištu se spodní dvěma vodiči tak, jak je naznačeno na obrázku. Lišty spolu nejsou vodivě spojené, o to se musíte postarat sami.

Máte? Ještě jednou si to prosím překontrolujte podle výše uvedeného postupu a obrázku. Pro jistotu stručné shrnutí:

1. Integrovaný obvod 74LS04 (74ALS04, 74HCT04) zasunutý tak, aby měl vývod číslo 1 vlevo dole – to znamená potisk čitelný, ne vzhůru nohama, a na levém okraji značku.

2. Vývod 14 (vlevo nahoře) připojený na +, vývod 7 (vpravo dole) připojený na -.

3. Spojené vývody 2 a 3 integrovaného obvodu (IO)

4. Spojené vývody 4 a 5 IO.

5. Mezi vývody 1 a 2 IO zapojený rezistor 10 K (před zapojením změřte!).

6. Mezi vývody 1 a 4 IO zapojený kondenzátor 10 μF. Vývod označený bílým proužkem na vývod 4 IO, druhý na vývod 1 IO.

7. Vývod 6 IO připojený na anodu LED (anoda = menší útvar uvnitř, delší vývod, hladký lem).

8. Katoda LED (= větší útvar, kratší vývod, seříznutý lem) připojená na jeden vývod rezistoru 330.

9. Druhý vývod téhož rezistoru připojený na mínus (-).

10. Horní i dolní napájecí lišty propojené – plus na plus, mínus na mínus.

11. Zdroj 5 V zapojený správně, nepřepólovaný.

![058-1.jpeg](images/00193.jpeg)

Zapněte napájení.

Bliká?

Pokud ano, tak hurá, sláva, haleluja, zvládli jste to. Pokud ne, nastává problém, a těch může být asi tak dvacet. Od těch banálních (na něco jste zapomněli, něco nemá správný kontakt, napájení nefunguje) přes závažnější (něco jste zapojili obráceně a je potřeba to otočit – nejčastěji LED, popřípadě jste použili nefunkční součástku) po fatální (něco jste zapojili obráceně, ono to potichu shořelo a přestalo fungovat a fungovat to nezačne, ani když to otočíte zpátky). Projděte si znovu celé zapojení, všechno si překontrolujte, změřte, jestli je na vývodech 7 a 14 napájecí napětí, zkuste otočit LED (prohodit vývody), jestli ji nemáte obráceně...

Pokud jste ale při sestavování postupovali pečlivě a přesně podle návodu, mělo by vše fungovat na první dobrou, takže se můžeme za intenzivního blikání naší první elektronické konstrukce podívat, co že se tam vlastně děje a proč. Protože cílem této knihy není ukázat vám, jak se postaví blikač, ale dát vám dostatek informací k tomu, abyste si ho dokázali navrhnout a postavit sami!

Ono to bohužel není tak úplně jednoduché a k tomu, abyste opravdu pochopili, proč blikač bliká, potřebujete spoustu teorie. Možná vás zklamu, ale nečekejte, že se ono tajemné mystérium blikače dozvíte hned v následující kapitole… Ale slibuju, že se k němu dostaneme – sice až v půlce knihy, ale věřte mi: to už budete vědět, jak funguje třeba kondenzátor a jakou má funkci, takže princip blikače bude naprosto zřejmý.

##### 3 Hlava, koleno, zem… {#3-hlava-koleno-zem}