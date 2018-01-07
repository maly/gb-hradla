## 35.3 Analogová cesta {#35-3-analogov-cesta}

Jde! Co by nešlo. Představte si takový rezistorový dělič, třeba ze čtyř rezistorů se stejnou hodnotou, k němuž jsou připojená tlačítka do společného bodu, který je přes pátý rezistor stejné hodnoty připojený k napájecímu napětí. Nějak takto:

![388-1.png](images/000388.png)

Za normálního stavu, pokud není žádné tlačítko stisknuté, je na výstupu napájecí napětí 5 V přes rezistor R5.

Když stisknete tlačítko S5, bude výstup připojen přímo na zem, a bude tam tedy rovných 0 voltů.

Když stisknete tlačítko S4, půjde proud přes rezistor R5, tlačítko S4 a rezistor R4 k zemi. Na výstupu bude 2,5 voltů, protože stiskem S4 vznikne dělič R : R, a jelikož jsou oba odpory stejně velké, bude výsledné napětí polovina napájecího.

Analogicky při stisku S3 bude dělič v poměru R:2R (R5 proti R3 + R4), tedy na výstupu bude cca 3,33 V.

Stisk S2 znamená dělení v poměru R:3R, tedy cca 3,75 V. Tlačítko S1 pak nastaví dělič na poměr R:4R, a výsledkem by mělo být napětí 4 volty.

No, a když výstup připojíte k analogovému vstupu Arduina, tak pomocí analogRead můžete číst přímo hodnoty stisknutých tlačítek. Dokonce můžete vynechat i R5 a použít interní pull-up – pinMode(A0, INPUT_PULLUP).

![389-1.png](images/000240.png)

Takže nakonec obsluhujete pět tlačítek pouhým jedním vstupem! Samozřejmě, takovéhle řešení má svoje limity: analogový převodník není nekonečně přesný, rezistory také nebývají přesné, navíc se „rozlaďují“ teplem, takže pět tlačítek je takové rozumné maximum.

Ale když už jsme na to narazili – existuje takové hezké zapojení, kdy pomocí rezistorů převádíte digitální signál na analogový. Samozřejmě existují velmi přesné součástky, digitálně-analogové převodníky (DAC), které tuhle práci dělají za vás. Dokonce jsou i v podobě malých obvodů, řízených třeba přes I2C nebo SPI. Ale když není zbytí, lze použít i jednoduché zapojení, které se nazývá R-2R.