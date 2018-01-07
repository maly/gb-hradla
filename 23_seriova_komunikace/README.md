# 23 Sériová komunikace {#23-s-riov-komunikace}

Co jsem v předchozí kapitole nakousl, to teď rozvedu. Sériová komunikace je totiž velmi používaná věc a téměř všechny moderní elektronické komponenty používají právě tento způsob komunikace, kdy jsou vícebitové informace (většinou osmibitové) přenášeny po bitech postupně za sebou.

Sériová komunikace si proto vystačí s jedním, dvěma, třemi či čtyřmi vodiči pro data, plus jedním vodičem pro zem. Společná zem je podstatná věc pro spojování zařízení, bez ní nám jednak chybí společný vztažný bod pro měření napětí, jednak při spojení tečou úplně zbytečné proudy, které mohou přetěžovat vstupní obvody. Mimochodem, všimli jste si někdy, že například u konektorů USB jsou některé kontakty delší?

![280-1.jpeg](images/00037.jpeg)

Důvod je prostý – delší vývody jsou napájení, takže při zasouvání se nejprve vodivě propojí napájecí obvody, a teprve potom se připojí datové signály.

Sériových rozhraní je několik druhů. Liší se od sebe nejen počtem vodičů, ale i schopnostmi a rychlostí.