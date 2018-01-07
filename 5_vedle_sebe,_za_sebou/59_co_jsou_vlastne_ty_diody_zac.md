## 5.9 Co jsou vlastně ty diody zač? {#5-9-co-jsou-vlastn-ty-diody-za}

Dioda je dnes většinou polovodičová součástka (dříve i v podobě elektronky), jejíž nejvýraznější vlastností je, že vede proud pouze jedním směrem. Má dva vývody, anodu a katodu, a vede proud pouze ve směru od anody ke katodě.

O diodách se ještě budeme bavit později, zde jen stručně…

Napětí určité výše je potřeba, aby se dioda vůbec „otevřela“, aby vedla proud. Takový je princip polovodičových přechodů, což si vysvětlíme později. Pokud je na diodě napětí menší, je zavřená – tedy její odpor je velmi vysoký a neteče skrz ni žádný proud, v žádném směru. Jakmile je na diodě napětí vyšší, dioda se skokově otevře (její odpor se velmi výrazně sníží) a proud může procházet – ovšem pouze v jednom směru.

Však si to sami zkuste. Nechte LED svítit, a pak ji otočte o 180 stupňů, prohoďte její vývody. Svítit nebude. V druhém směru („závěrném“) je dioda zavřená. Zase až do určité velikosti napětí, tentokrát zvaného průrazné. Pokud zapojíme vyšší napětí v závěrném směru, dioda se rychle zničí. Viz následující obrázek, který ukazuje závislost proudu na napětí, připojeném k (obecné) diodě.

V pravé části grafu je dioda zapojená v dopředném – průchozím směru. Proud teče velmi malý, a až u hranice VF se dioda otvírá a vede proud velmi dobře, téměř s nulovým odporem.

V závěrném směru, tedy vlevo od svislé osy, prochází velmi malý proud. V bodě VBR (Breaking Voltage, průrazné napětí) se dioda zničí, „prorazí“, a přestane fungovat. Dopředné napětí bývá nízké, okolo desetin až nízkých jednotek voltů, průrazné je o řády větší – podle typu třeba 50 voltů, ale i 1000.

![104-1.png](images/000215.png)

Speciální variantou diody je Zenerova dioda. Ta se při určitém napětí v závěrném směru „prorazí“, ale vratně. Proto se používá ke stabilizaci či přepěťové ochraně. Jakmile napětí překročí danou mez, dioda se otevře, vede proud, a tím snižuje napětí.

[eknh.cz/dioda](https://eknh.cz/dioda)

V číslicové technice se s diodami setkáme poměrně často. Používají se například k ochraně obvodů před přepólováním. Dříve se diody používaly v těch nejjednodušších přijímačích – krystalkách, což byly vděčné obvody pro amatéry, s nimiž jste pomocí několika součástek mohli poslouchat rozhlasové vysílání v pásmech AM. Diody se také používají k usměrňování střídavého napětí. V této knize se ale těmto oblastem nebudu věnovat šířeji a zájemce odkážu na jinou literaturu.

Ale myslím, že je právě teď vhodná chvíle udělat opět malou odbočku. Podíváme se, kde zjistit ta čísla, kterými tu šermuju, jako 0,7 V a 50 V. To jsem tak chytrý a Aštar Šeran mi ta čísla vnukl skrz alobalovou čepičku? Ale kdepak, podíval jsem se do datasheetu.

Do čeho že?

Do datasheetu!