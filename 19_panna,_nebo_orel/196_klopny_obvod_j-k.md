## 19.6 Klopný obvod J-K {#19-6-klopn-obvod-j-k}

Nebojte, tento je poslední, a zmíním se o něm jen pro úplnost. Zas tak často se totiž v praxi nepoužívá… Dřív se z těchto obvodů skládaly například čítače, ale dnes už jsou takové obvody dostupné v integrované podobě, takže se s ryzím obvodem J-K skoro nepotkáte.

![240-1.png](images/000073.png)

Klopný obvod J-K je vlastně kombinací jednoduchého klopného obvodu R-S a klopného obvodu typu T. Pokud jsou J a K v logické 0, drží obvod svůj stav. Pokud je J = 0 a K = 1, nastaví se obvod do logické 0\. Pokud je J = 1 a K = 0, nastaví se obvod do logické 1\. No a konečně pokud jsou oba vstupy v log. 1, přepne se s každým hodinovým pulsem obvod do opačného stavu, než byl předtím.

I tento klopný obvod najdete v řadě 74xx – nejznámější jsou typy 7470 a 7472\. U těchto obvodů jsou vstupy J a K dokonce trojité – /J0, J1, J2 a /K0, K1, K2\. Jeden je negovaný, dva obyčejné, a uvnitř se skládají pomocí hradla AND: K = /K0 AND K1 AND K2\. K tomu, aby byl vstup K aktivní, musí nastat kombinace K0 = 0, K1 = 1, K2 = 1\. Obdobně pro vstup J.

Klopné obvody tvoří základ veškerých složitějších číslicových strojů. Jejich zásadní vlastností je, že si dokáží pamatovat, a tím do systému vnáší prvek času. „Něco“ se stane v pravidelných intervalech, „něco“ se stane až poté, co se stalo něco jiného…

##### 20 Čítače {#20-ta-e}