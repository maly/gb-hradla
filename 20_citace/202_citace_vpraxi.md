## 20.2 Čítače v praxi {#20-2-ta-e-v-praxi}

Čítače se samozřejmě, jak jinak, vyrábí i jako integrované obvody v řadě 74xx. Dva nejběžnější jsou 7490 a 7493\. Jeden z nich je čtyřbitový asynchronní binární, druhý čtyřbitový asynchronní desítkový (to jako že počítá 0-9). Který je který? Mnemotechnická pomůcka: 7490 má na konci 0, stejně jako 10 má na konci nulu, takže 7490 je desítkový, 7493 je binární (vlastně „šestnáctkový“).

![245-2.jpeg](images/00091.jpeg)![246-1.png](images/000126.png)

Oba obvody mají stejné zapojení vývodů, jen u typu 7490 je zapojený vnitřní resetovací obvod pro stav 1010 (= 10 v desítkové soustavě), čímž se zkracuje cyklus, a má navíc vstupy R9.

Všimněte si několika věcí: nulovací vstup není jeden, jsou dva, a jsou uvnitř zapojeny s hradlem NAND, takže k vynulování je potřeba stav R0(1) = R0(2) = 1\. Což se nám hodí, viz výše – až budeme zkracovat cyklus na 6 hodnot, tak nemusíme zapojovat už nic navíc.

U čítače 7490 jsou navíc dva vstupy, označené R9(1) a R9(2). Funkce je obdobná vstupům R0: pokud jsou oba v log. 1, tak se čítač nastaví do stavu 9 (1001).

Další věc je zase zapojení napájecích vývodů. Tyto obvody opět nedodržují tradiční napájení, podobně jako obvod 7475, tak je na to třeba dát pozor.

No a poslední věc, na kterou musím upozornit, je ta, že čítače nejsou plně čtyřbitové. Jsou uvnitř vlastně dva, jeden jednobitový, jeden tříbitový. První má hodinový vstup CKA (někdy jen A) a výstup QA, druhý má vstup CKB (někdy značený jen B) a výstupy QB, QC a QD. Pokud chceme, aby obvod fungoval tak, jak jsem ho popsal, tedy jako čtyřbitový, zapojuje se výstup QA na vstup CKB.

![247-1.png](images/000098.png)

Pro zajímavost – takhle vypadaly katalogové informace z katalogu Tesla v 80\. letech:

![247-2.png](images/000146.png)![247-3.png](images/000102.png)

Můžete si za sebe zapojit desítkový čítač 7490 a za něj binární čítač 7493 se zkráceným cyklem na 6\. Využijte k tomu oba vstupy R0:

![248-1.png](images/000172.png)

Na hodnoty 0 až 5 ale stačí jen tři bity, můžete proto využít jen tříbitový čítač B a výstupy QB, QC a QD:

![248-2.png](images/000109.png)

Všimněte si, že jsem nevyužitý vstup A připojil k napájecímu napětí. Už jsem to zmiňoval, a připomenu to znovu: Nevyužité vstupy nikdy nenechávejte „bimbat“ jen tak ve vzduchu, vždy je připojte buď k zemi, nebo k napájecímu napětí.