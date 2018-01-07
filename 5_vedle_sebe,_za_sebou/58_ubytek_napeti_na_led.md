## 5.8 Úbytek napětí na LED {#5-8-bytek-nap-t-na-led}

Zapojte si LED s rezistorem tak, aby LED svítila. Vyberte si třeba červenou LED a rezistor 220 ohmů. Napájecí napětí bude 5 V. Víme, že proud, protékající rezistorem, bude U / R = 5 / 220 = 0,022 A, tedy 22 mA. To je pro většinu LED proud na hranici bezpečného provozu. Pokud byste zapojili LED bez omezujícího odporu, poteče jí plný proud, který může zdroj dát, a LED spálíte! Pozor na to!

Je pravda, že ve mne teď hlodá zlomyslný červíček, který vám chce doporučit, abyste si to zkusili. Fakt, vzít zdroj, třeba nabíječku k telefonu, připojit k němu holou LED, a sledovat to prsk, kterým se s vámi LEDka rozloučí. Abyste si to pamatovali. Ale myslím, že se vám to určitě brzy podaří neúmyslně…

Změřte proud, který obvodem teče, a změřte, jaký je úbytek napětí na LED a na rezistoru. Pokud máte červenou LED, tak úbytek napětí na ní bude zhruba 1,8 voltů, na rezistoru pak ten zbytek do celkového napájecího napětí (při 5 V to bude zhruba těch 3,2 voltů).

_Všimněte si, že jsem v předchozím textu nenapsal, jestli máte zapojit rezistor mezi katodu a zem, nebo mezi anodu a kladné napětí. Je v tom nějaký rozdíl? Neptejte se, zkuste si to, přinejhorším si zničíte diodu._

Máte? Teď už asi víte, že jste si diodu nezničili, a že je úplně jedno, jestli rezistor zapojíte před diodu, nebo za diodu...

Zkuste zapojit druhou diodu do série s tou první. Tedy třeba mezi katodu a záporný pól připojte druhou LED tak, že anodu zapojíte na katodu předchozí diody, a katodu diody 2 zapojíte na zem. Svítí? Svítí. A co třetí dioda do série, svítí i ta? Za chviličku si řekneme víc...

Teď _do série_ zapojíme potenciometr – třeba 1k, ale klidně i s větším odporem. Využijeme jeden z krajních vývodů a prostřední vývod, druhý krajní necháme nezapojený. Když budeme teď potenciometrem otáčet, uvidíme, že se LED rozsvěcí a zhasíná podle toho, jak otáčíme. K pevnému rezistoru 220 ohmů se přičítá proměnný odpor rezistoru, a podle natočení kolísá od 0 do Rmax.

[eknh.cz/ledpot](https://eknh.cz/ledpot)

Máte? Teď si zkuste změřit proud, který teče LEDkou, a napětí, jaké na ní je, a to pro různá nastavení jezdce. Můžete zapojit i výpočetní techniku, zanést si hodnoty do tabulky a udělat si graf, kde na vodorovné ose bude úbytek napětí na diodě, na svislé pak proud.

Pokud si takový graf nakreslíte, získáte tak něco, čemu se říká „voltampérová charakteristika“. Mně to vyšlo nějak takto:

![102-1.png](images/000196.png)

(Vodorovně volty, svisle miliampéry)

Když si tedy spočítám, jaký je odpor LED (R = U / I), tak zjistím, že se mění podle velikosti proudu. Čím větší proud, tím menší odpor. Součástky, jako jsou diody (tedy i LED, což je „Light Emitting Diode“), se nazývají nelineární, protože jejich odpor není konstatntní a proud, který jimi prochází, není čistě závislý na napětí. Rezistory jsou lineární (pokud tedy zanedbáme změny odporu v důsledku zahřívání procházejícím proudem).

Když budeme proud, tekoucí skrz LED, snižovat, bude její odpor růst, naopak při zvyšování proudu odpor klesá a při překročení určité meze dojde k nevratnému poškození.

Všimněte si, že úbytek napětí na LED je víceméně konstantní a pohybuje se okolo 1,8 voltů. Toto napětí je dáno fyzikálními vlastnostmi – u červených LED se pohybuje pod hranicí dvou voltů, u infračervených (např. v dálkových ovladačích TV) je okolo 1,5 V, u zelených nad 2 V, u modrých pak i přes 3 volty. Obecně se dá říct, že čím kratší vlnová délka světla, tím vyšší úbytek napětí.

U normálních polovodičových diod, tedy těch, co nesvítí, je tento úbytek zhruba 0,7 voltu (opět se mění podle proudu, který diodou teče). Toto napětí se může lišit podle technologie, u starších a dnes už méně běžných germaniových diod to bývá okolo 0,2 voltu, u takzvaných Schottkyho diod to bývá mezi 0,15 – 0,4 voltu. Úbytek napětí se v literatuře označuje VF (z anglického Voltage Forward).

| Vlnová délka (nm) | Světlo | VF při proudu 20 mA | Materiál |
| --- | --- | --- | --- |
| 940 | Infračervené | 1,5 V | GaAlAs / GaAs |
| 635 | Červené | 2 V | GaAsP / GaP |
| 570 | Zelené | 2 V | InGaAlP |
| 430 | Modré | 3,8 V | SiC / GaN |