## 14.4 Vícevstupová hradla {#14-4-v-cevstupov-hradla}

Ještě jsme si neřekli, i když si to mnozí z vás asi odvodili, že existují i vícevstupová hradla – v praxi se používají třívstupová, čtyřvstupová a osmivstupová, ale při syntéze obvodů v logických polích si klidně nadefinujeme třináctivstupové AND. Funkce je podobná těm dvouvstupovým, jen si slovo „oba“ nahraďte slovy „všechny“ (AND). Tedy: Výsledkem AND je 1, pokud všechny vstupy jsou 1, jinak 0\. OR je 1, pokud alespoň jeden vstup je 1, jinak 0.

Schválně, co udělá třívstupový XOR? Třívstupový XOR je v logické 1 tehdy, pokud je na vstupu právě jedna logická 1, nebo pokud tam jsou tři. V logické 0 je, pokud na vstupu nejsou žádné jedničky, nebo pokud tam jsou dvě. Obvod XOR tak vlastně počítá lichou paritu.

Lichá parita (Parity Odd) nějakého vícebitového signálu je jednobitový údaj, který je logická 1 tehdy a jen tehdy, pokud je počet logických 1 v signálu lichý. Paritní bit se používá pro jednoduchou kontrolu správnosti dat: pokud je jeden bit poškozen (má opačnou hodnotu), parita nesedí. Na více bitů bohužel jednoduchá parita nesedí. A ano, je i sudá parita (Parity Even), která má přesně opačnou funkci.