## 13.7 U-káz-ka! U-káz-ka! {#13-7-u-k-z-ka-u-k-z-ka}

Dobrá, pojďte si zazapojovat.

Vezměte si obvod 7400\. Teď už víte, že jeho označení bude třeba SN74ALS00, nebo SN74HCT00, nebo klidně i MH74LS00, nebo jen 74HC00, nebo … v podstatě cokoli z kombinace _xx74xx00xx_. Prostě nějaký takový obvod vezměte a zapojte ho do nepájivého pole stejně, jako jste to dělali v první kapitole. Pamatujete? Pěkně doprostřed, a podívejte se na něj – klíč, ta značka na pouzdru, ať je hezky vlevo, ať máme vývod číslo 1 vlevo dole.

Pokud si nepamatujete, nalistujte si první kapitolu, zapojování blikače _– orientaci obvodu určíte podle popisku a výlisku na pouzdru, pokud máme popisky správně orientované a výlisek vlevo, tak vlevo dole je vývod 1, vedle něj 2, a číslování pokračuje ve spodní řadě doprava. Na konci pokračuje proti směru hodinových ručiček nahoře, zprava doleva._

Tak. Obvod bychom měli. Co s ním? Jak zjistíte, co máte kam připojit? No, schválně, kdo si to pamatuje? Správně, podíváte se do datasheetu. Ale protože jsem na vás hodný, tak vám sem ten nejdůležitější obrázek zkopíruju. To je on:

![142-1.png](images/000368.png)

Vidíte, jak je uspořádaný obvod uvnitř: jsou tam čtyři hradla NAND, zapojená na vývody 1-2-3, 4-5-6, 13-12-11 a 10-9-8\. Vývod 7, označený GND, je zem (Ground), tedy pro nás záporný pól napájecího zdroje, vývod 14 je Vcc, neboli napájecí napětí.

Jak poznáte, který vstup je A a který B? Nepoznáte. Je to přeci úplně jedno! U hradla NAND můžete vstupy zaměnit.

Pamatujte si: Napájecí napětí se ve schématech značí buď Vcc, nebo Vdd, nebo prostě „+ 5 V“; zem je GND, Vss, Vee, nebo „0“. Proč? No, protože kladný pól, tedy napájecí napětí, bývá spojeno s kolektorem tranzistorů u obvodů TTL (odtud Vcc – Voltage Collector), případně s elektrodou Drain u MOS (Vdd – Voltage Drain). Analogicky Vee bude souviset s emitorem (TTL), Vss s elektrodou Source (MOS). Ale pro nás je Vcc totéž jako Vdd, a Vss budiž totožné s Vee i s GND.

Napájecí napětí se tedy připojuje stejně jako u blikače. Podíváme se na funkci jednoho hradla. Třeba toho, jak má vstupy 1 a 2 a výstup 3\. Na výstup (nožička číslo 3) si připojte LEDku (samozřejmě přes rezistor 330 ohmů!). Vstupy (1 a 2) propojte se zemí (se záporným pólem napájení). Oba.

Co s těmi ostatními hradly v pouzdru? Teď nic, ale v reálných konstrukcích je dobré připojit jejich vstupy k některému pólu napájení, ideálně oba k + 5 V. Vývody mohou zůstat nezapojené, pokud dané hradlo nepoužíváte. Proč? No, pokud ty nepoužité necháte úplně nezapojené, mohou se vlivem rušení náhodně překlápět, čímž budou zvyšovat odběr a přenášet rušení do napájecího vedení.

Když teď zapnete napájení, měla by LED svítit. Oba vstupy spojené se zemí znamenají, že na vstupech jsou hodnoty 0, a výsledek 0 NAND 0 = 1.

Když teď oba vstupy připojíte na kladný pól napájení, LED zhasne.

Otázka: Můžete to dělat při zapnutém napájení? Odpověď správná: Ne, nikdy to nedělejte! Odpověď realistická: Sice to někteří někdy dělají a nic se nestane, ale nezvykejte si na to a fakt to radši nedělejte, protože občas se holt něco stát může, a hezké to nebude…

Zkuste si přepojováním vstupů 1 a 2 nasimulovat všechny možné kombinace vstupních hodnot a podívat se, jaký bude výstup.

Pokud vám LED nesvítí vůbec, máte problém. Zkuste ji nejprve přepojit místo na vývod číslo 3 na napájecí napětí. Samozřejmě přes ten rezistor. Pokud stále nesvítí, může to mít tři příčiny: Máte LED obráceně (vzpomeňte si na kapitolu o diodách), máte LED spálenou, nebo vám nefunguje napájení.

Pokud vám LED svítí naopak pořád, i když zapojíte vstupy 1 a 2 na napájecí napětí, máte pravděpodobně vadný obvod 7400\. Zkuste to popřepojovat jinak, třeba na vstupy 4, 5 a výstup 6.

_Jde ty vstupy udělat jinak, než pomocí drátků?_

Jasně že to jde. Jako vstup můžeme použít třeba tlačítko, nebo přepínač.