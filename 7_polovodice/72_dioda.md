## 7.2 Dioda {#7-2-dioda}

Ano, polovodičová dioda je ve skutečnosti přesně toto – jsou to dva maličké kousky polovodičů P a N, spojených dohromady tak, že tvoří přechod. K těmto polovodičům jsou připojeny vývody – u P je to anoda, u N katoda.

Teď už je jasné, jak je možné, že diodou prochází proud jen jedním směrem. Ostatně – dobrou pomůckou je už samotný symbol diody, kde trojúhelník tvoří malou šipku. Ta ukazuje směr, kterým diodou teče proud – od anody ke katodě.

![87-1.png](images/000111.png)

Mimochodem, když už je řeč o schematických značkách – víte, jaký je rozdíl mezi následujícími symboly?

![87-2.png](images/000169.png)

Všechny symboly označují totéž: diodu. Jen se v různých dobách kreslily různě. Dřív se hodně dbalo na ten kroužek okolo symbolu (kroužek symbolizuje pouzdro součástky). Setkáte se ale při čtení schématů se všemi. Hlavní rozdíl je, že jen jeden z nich je podle platné normy (je to ten druhý zleva). Měli byste tedy používat ten normovaný. Co ale naděláte, když zrovna ten váš program, který ke kreslení použijete, bude mít symbol pro diodu jiný? Upřímně řečeno: neřešil bych to. Pokud bude poznat, že to je dioda, tak v pořádku. (Což je zase rada strýčka bastlíře.)

Když se místo klasického křemíku použijí jiné látky, například galiumarsenid (GaAs), bude energie, která se v diodě ztrácí při „zapadávání elektronů do děr“ (laicky řečeno) vyzářena jako viditelné světlo. Vzniká tak LED, neboli světlo emitující dioda (Light Emitting Diode). Různé látky vydávají různé barvy světla, a tak máme k dispozici celou škálu barev LED. Nejstarší byly červené, pak přišly žluté a zelené, a když byla objevena látka, která vydává modré světlo, bylo možné sestrojit RGB LED a vytvářet libovolnou barvu světla. Existují i LED, které vydávají světlo ultrafialové a infračervené (infračervené LED se používají u dálkových ovladačů televizí apod.)

P-N přechod je samozřejmě stále citlivý na dodávání energie zvenčí – proto jsou polovodičové součástky většinou v neprůsvitném obalu, aby je neovlivňovalo světlo. I tak je ale může ovlivňovat teplo a měnit jejich charakteristiku. Se vzrůstající teplotou klesá jejich odpor a roste šum.

Někdy je ale citlivost na světlo vítaná – existují speciální diody, které mají průsvitné pouzdro, a u nich se právě citlivost na světlo a snižování odporu v závěrném směru používá k detekci světla. Proto se jim říká fotodiody.

Samotný P-N přechod, pokud je osvětlen, dokonce elektrické napětí vytváří přímo ze světla. Jestli tipujete, že to je princip solárních článků a panelů, jste na správné stopě.

Jak se říká – kdo nevěří, ať tam běží. Zkuste si to sami: Vezměte LED, připojte k jejím vývodům voltmetr, přepnutý na hodně nízký rozsah, a posviťte na ni jasným světlem…

Můžete si zkusit různobarevné LED, a uvidíte, pro kterou barvu se vám podaří získat největší napětí.

Diod existuje víc typů – už jsem zmínil Zenerovu diodu, která slouží ke stabilizaci napětí. Zajímavým typem diod jsou Schottkyho diody – zde je na místě jedné elektrody použit místo polovodiče kov. Taková dioda má nižší dopředné napětí a je rychlejší – rychleji se uzavírá a otevírá.