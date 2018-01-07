## 20.5 Ještě nějaké čítače? {#20-5-je-t-n-jak-ta-e}

Samozřejmě, že jsou na skladě. Třeba takový Johnsonův čítač.

Představme si řetěz obvodů typu D, podobně jako u výše zmíněných čítačů. Každý vstup D je připojen na výstup Q předchozího obvodu. Vstup D prvního obvodu v řadě je zapojen na invertovaný výstup /Q posledního obvodu.

Všechny klopné obvody mají spojený vstup CLK, a všechny mají vyvedený vstup CLR (Reset).

![260-1.png](images/000259.png)

Začíná se od stavu 0000, a čítač nabývá postupně hodnot 0000, 0001, 0011, 0111, 1111, 1110, 1100, 1000 – a pak zase od 0000\. Počítá tedy v takzvaném „Johnsonově kódu“…

### 20.5.1 Johnsonův kód {#20-5-1-johnson-v-k-d}

Klasický binární kód má jednu nevýhodu – někdy se mění hodnota více bitů najednou, třeba při přechodu ze stavu 0011 do stavu 0100 se mění rovnou tři bity. Pokud změna probíhá pomaleji a ne (ideálně) najednou, objeví se postupně sekvence velmi rychlých změn, např. 0011 -&gt; 0010 -&gt; 0000 -&gt; 0100\. Pokud je další zařízení dostatečně rychlé, může tyto změny zaznamenat a fungování obvodů bude narušené. Někdy to lze vyřešit změnou obvodového řešení, ale někdy taková možnost není. Proto se používají i kódy, kde se při přechodu mezi stavy mění vždy hodnota jednoho jediného bitu. Johnsonův kód je příklad jednoho takového kódu. Pro N bitů může nabývat 2N kombinací, jak jsme si ukázali výš.

Čtyřbitový Johnsonův kód tvoří postupně tyto hodnoty: 0000, 0001, 0011, 0111, 1111, 1110, 1100, 1000.

### 20.5.2 Grayův kód {#20-5-2-gray-v-k-d}

Další podobný kód je kód Grayův. Vychází z binárního kódu, ale čísla jsou přeuspořádaná tak, že mezi dvěma po sobě následujícími stavy se také mění hodnota právě jednoho jediného bitu:

| Hodnota | Binárně | Grayův kód |
| --- | --- | --- |
| 0 | 0000 | 0000 |
| 1 | 0001 | 0001 |
| 2 | 0010 | 0011 |
| 3 | 0011 | 0010 |
| 4 | 0100 | 0110 |
| 5 | 0101 | 0111 |
| 6 | 0110 | 0101 |
| 7 | 0111 | 0100 |
| 8 | 1000 | 1100 |
| 9 | 1001 | 1101 |
| 10 | 1010 | 1111 |
| 11 | 1011 | 1110 |
| 12 | 1100 | 1010 |
| 13 | 1101 | 1011 |
| 14 | 1110 | 1001 |
| 15 | 1111 | 1000 |

Grayův kód se používá místo binárního tam, kde by případná změna více bitů nemusela proběhnout přesně ve stejný čas. Navíc se poměrně snadno převádí na binární a zpět, pomocí operace XOR. Pokud si bity binárního kódu označíme jako b3-b0 a Grayova kódu jako g3-g0, tak převodní vzorce jsou jednoduché:

g0 = b0 XOR b1

g1 = b1 XOR b2

g2 = b2 XOR b3

g3 = b3 XOR 0 = b3

Tedy vždy jako XOR daného bitu a bitu o řád vyššího (u nejvyššího bereme nulu).

Představte si, že máte cosi, co se otáčí, a vy chcete vědět, jakým směrem je to natočené. Pro jednoduchost řekněme, že vám to stačí znát s přesností plus minus 45 stupňů. Připevníte k otáčivé věci kolo, to si rozdělíte na osm segmentů, a protože osm hodnot zakódujete do tří bitů, tak si uděláte tři soustředné kružnice. A v nich si některé segmenty vybarvíte a jiné ne, takže pak budete moci prostým způsobem, třeba optickým snímačem, určit, jak je kolo natočeno.

První pokus bude vypadat nějak takto:

![262-1.png](images/000324.png)

Jenže stačí drobná nepřesnost, a hned v pozici „nahoře“ vám vznikne přechod 001 – 011 – 010, popřípadě 001 – 000 – 010\. Když použijeme Grayův kód, nic takového nehrozí:

![262-2.png](images/000280.png)