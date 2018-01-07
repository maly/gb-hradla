## 14.6 Zjednodušování logických výrazů {#14-6-zjednodu-ov-n-logick-ch-v-raz}

Na logické výrazy můžeme s trochou dobré vůle nahlížet podobně jako na aritmetické – i zde existují například operace sčítání a násobení (OR, AND), i tyto operace mají neutrální prvek 0, resp. 1, i tyto operace jsou komutativní (lze prohodit operandy) a asociativní, i zde lze krátit a dělat podobné operace. Nejčastější situace, kdy je potřeba pracovat s těmito funkcemi, je tehdy, když máte daný „black box“, tedy nějaký obvod s určitým počtem vstupů a výstupů, k tomu dostanete pravdivostní tabulku, tedy seznam požadovaných hodnot při určitých vstupních kombinacích, a vy máte navrhnout z hradel ekvivalentní zapojení.

V číslicové technice platí, že libovolný výraz, zadaný pomocí tabulky hodnot, můžeme převést na součet součinů (popřípadě součin součtů), a to nad vstupními signály a jejich negacemi. Tedy třeba (A AND B) OR (NOT B AND C) OR (C AND NOT D AND E)... V praxi se k takovému zjednodušení používají různé metody – [Karnaughova mapa](https://en.wikipedia.org/wiki/Karnaugh_map), [algoritmus Quine-McCluskey](https://en.wikipedia.org/wiki/Quine%E2%80%93McCluskey_algorithm)...