## 39.3 Co s daty v Sigfoxu? {#39-3-co-s-daty-v-sigfoxu}

Veškerá data, co přes Sigfox pošlete, skončí v backendu této služby – je to centralizovaná cloudová služba, a všechna data protékají skrz server provozovatele. Za normálních okolností tam skončí, a vy si je můžete přečíst nebo exportovat. Ovšem backend Sigfox nabízí i možnost zprávy přeposlat – používá k tomu zase jednoduché http(s) volání GET s možností předat data surová, nebo jednoduše parsovaná. K tomu získáte i informace o pozici vysílače, o síle signálu, přesném čase vyslání zprávy atd.

Sigfox umožňuje i zpětný přenos dat, ale nikde není zaručeno, že se data na zařízení opravdu dostanou. Zpětný přenos funguje pouze jako doplněk vysílání (de facto odpověď na vysílání). Je vhodný maximálně pro nějaké servisní informace, přepínání módů apod. Rozhodně nemůže fungovat jako regulerní zpětný kanál, např. pro ovládání zařízení.

Důležité u sítě Sigfox je, že není garantováno doručení zprávy. Zpráva se vysílá několikrát, aby se zvýšila pravděpodobnost, že bude zachycena, ale pokud se tak nestane, nikdo se to nedozví – ani zařízení, ani příjemce.

Schéma a zdrojový kód najdete na [eknh.cz/sigfox](https://eknh.cz/sigfox)

##### 40 Šťastnou cestu… {#40-astnou-cestu}
