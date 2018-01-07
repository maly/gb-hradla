## 3.8 Výkon {#3-8-v-kon}

Proud nám teče vodičem kolem dokola, to je moc hezké, ale sám o sobě nic užitečného nedělá. Musí se někde spotřebovávat. Nejjednodušší spotřebič je třeba stará dobrá žárovka – to je tenké kovové vlákno, které má poměrně vysoký odpor. Pokud proud překonává odpor, část elektrické energie se přeměňuje v tepelnou. Množství takto přeměněné energie se nazývá výkon, měří se ve wattech (W), označuje se P a jeho velikost je rovna součinu proudu a napětí, tedy P = U . I.

Elektrický výkon je pro nás velmi užitečná veličina, protože udává nejen to, jak silný spotřebič máme (žárovku, motor apod.), ale na druhé straně i to, kde elektřinu zbůhdarma pálíme. Pokud zapojíme rezistor 330 ohmů na baterii 1,5 V, poteče jím proud 4,54 mA, a to znamená, že výkon, který se na něm „protopí“, bude 6,8 mW. To zvládnou i miniaturní rezistory. Ovšem někdy se stane, že navrhneme obvod, kterým poteče velký proud, a pak se může snadno stát, že spotřebovaný výkon bude tak velký, že nezbyde než použít pořádně velké součástky a intenzivně chladit! Hodně „topí“ například stabilizátory napětí ve zdrojích, výkonové zesilovací prvky, nebo mikroprocesory.

Mimochodem, když si do předchozího výrazu P = U . I dosadíte podle Ohmova zákona (U = R . I), tak zjistíte, že lze výkon vyjádřit i pomocí odporu a proudu, jako P = R . I . I = R . I2. Tedy že výkon je přímo úměrný odporu, který proud překonává, a druhé mocnině velikosti proudu. Což je důvod, proč se pro dálkový přenos elektřiny používá velmi vysoké napětí s malými proudy: snižují se tím ztráty ve vedení. Elektrické vedení o délce 100 kilometrů má nezanedbatelný odpor, a máme jedinou možnost, jak snížit „propálený výkon“: snížit procházející proud. A k tomu, abychom mohli snížit proud, potřebujeme zvýšit napětí.

![070-1.jpeg](images/00265.jpeg)

Zkuste si to spočítat:

V zásuvce máme 230 voltů, odebrat z ní můžeme 6 ampérů. Výkon, který nám zásuvka poskytne, je tedy 230 . 6 = 1380 wattů (1,38 kW). Kdybychom tuto energii přenášeli od elektrárny až do domu napětím 230 voltů, potřebujeme přenést vodičem zmíněných 6 ampérů. Kdyby mělo vedení odpor 0,3 ohmu na kilometr, což je přibližně reálná hodnota, bude jeho celkový odpor 30 ohmů, a výkon, který se po cestě spálí, bude 30 . 62 = 1080 wattů!

Když zvýšíme pro přenos napětí tisícinásobně, tedy na 230 000 voltů (230 kV – ve skutečnosti se používá velmi blízká hodnota 220 kV, i vyšší), stačí nám tisíckrát menší proud, tedy 6 mA. Přenesený výkon stále odpovídá: 230000 . 0,006 = 1380\. Jenže na stejném vedení o odporu 30 ohmů spálí proud 0,006 A pouze 30 . 0,0062 = 0,00108 wattu. Ano, vidíte dobře: 1,08 miliwattu, což je miliontina oproti předchozímu případu.

To je důvod, proč je v dálkovém vedení velmi vysoké napětí. Není to proto, aby bylo nebezpečné dotýkat se drátů i na zem spadlých, ale proto, že při vedení na dlouhé vzdálenosti je výhodnější vést vyšší napětí a menší proud.

[eknh.cz/vedeni](https://eknh.cz/vedeni)

Jazyková vsuvka

Je „ten ampér“, nikoli „ta ampéra“. Takže doma máte jistič (třeba) na 25 ampérů, nikoli na 25 ampér. Důvod je jednoduchý: Ampér, jako jednotka proudu, je pojmenován po francouzském matematikovi, který se jmenoval André-Marie Ampère, a přestože tam může mást ta Marie, tak vězte, že to byl muž. Proto ten ampér a proud má velikost pět ampérů, nikoli pět ampér.

Volt problém nedělá – a přitom se fyzik, po kterém nese název jednotka napětí, jmenoval Alessandro Volta. Třetí do party je německý fyzik Georg Simon Ohm, po němž je pojmenována jednotka elektrického odporu. Jen pro jistotu – čte se to [óm].

Čtvrtý kolega je Skot James Watt, a s ním jsou taky obtíže. Leckdo je schopen říct, že „spotřeboval sto kilowatt“ – jenže ona není žádná „kilowatta“! Tu si schovejte, až budete nakupovat obvazy. V elektrotechnice vždy a pouze „sto kilowattů“. Navíc, a to dodávám na okraj, se spotřeba neměří ani v kilowattech, ani v kilowattách, ale v kilowatthodinách.