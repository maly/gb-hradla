## 15.1 Víc sedmisegmentovek… {#15-1-v-c-sedmisegmentovek}

Na Aliexpressu nebo eBay najdete mnoho hotových modulů se sedmisegmentovkami. Většinou používají čínské obvody TM16xx, popřípadě obvody Maxim MAX72xx. Jeden z oblíbených typů je osmimístný displej s obvodem MAX7219\. Tento obvod v zásadě funguje podobně jako naše oblíbené posuvné registry, jen místo osmi segmentů dokáže budit až 64 segmentů (8 pozic po osmi segmentech). Pomocí jednoduchého sériového rozhraní (CLK a MOSI) pošlete do obvodu 16bitové řídicí slovo, které nastavuje segmenty, zapíná a vypíná dekodér znaků nebo řídí intenzitu, a pulsem na vstupu LOAD jej nahrajete do registrů (a tedy provedete). Výhodou je, že obvod MAX7219 je průchozí, a je tedy možné naskládat takových displejů za sebe několik.

![189-1.jpeg](images/00343.jpeg)

Když může takový obvod budit 64 LED segmentů, tak kde je psáno, že to musí být jen sedmisegmentovky? Může to být klidně i matice diod:

![190-1.jpeg](images/00407.jpeg)

Takové matice můžete zase pospojovat za sebe a vytvořit z nich například displeje, podobné těm, co v MHD ukazují názvy stanic. Dokonce existují i velmi jednoduché herní konzole s takovými displeji (ovšem s RGB LED):

![191-1.jpeg](images/00362.jpeg)

Málokdy budete s takovými obvody pracovat napřímo, většinou budou skryté v nějakém modulu spolu s LED a omezovacími rezistory. Když je o tom řeč – nezapomeňte, že LED jsou sice málo náročné na proud, ale když jich je 64, tak se to nasčítá…

##### 16 Jak vypadá hradlo uvnitř {#16-jak-vypad-hradlo-uvnit}