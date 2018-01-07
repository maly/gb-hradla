## 5.1 Svítilna s LEDkou {#5-1-sv-tilna-s-ledkou}

Úplně nejjednodušší zapojení je taková obyčejná svítilna. Třeba právě s LEDkama. Jak funguje? No, je to jednoduché: máte zdroj energie, třeba baterii, a LEDku, a mezi tím rezistor. Nějak takhle:

![093-1.png](images/000075.png)

Zkuste si to zapojit. Prozradím vám předem, že když na místě baterie použijete monočlánek s napětím 1,5 voltu, tak vám to svítit nebude. Musíte použít alespoň dva za sebou, ještě lépe plochou baterii (v níž jsou tři za sebou), nebo například Arduino, z něhož můžete odebírat + 5 voltů.

Rezistor použijte třeba náš oblíbený 330R. U baterie 4,5 voltů propustí 4,5/330 = 13 mA, což je dostatečný proud na to, aby LED svítila, a zároveň bezpečný natolik, aby se nepřepálila. Když chcete, aby LED svítila víc, můžete zkusit snížit velikost odporu – můžete jít třeba na 220R, pak bude proud skoro 20 mA, a to je pro většinu LED maximum.

Jenže co když chcete svítit víc, ještě víc? Jak na to? No, co třeba zapojit víc, víc diod? Zkuste si to. Zapojte si dvě najednou…

Jak? No, v zásadě máte čtyři možnosti, jak místo jedné LED zapojit dvě:

![093-2.png](images/000088.png)

Možnosti 1 a 3 dávají smysl. Vyzkoušejte si je, při které z nich budou LED svítit nejvíc. Možnost 2 je nefunkční, takhle vám LED svítit nebudou. Možnost 4 je zajímavá v tom, že takhle vám bude svítit vždy alespoň jedna LED, i když přepólujete zdroj, přehodíte kladný a záporný pól, ale většího jasu nedosáhnete…

A co když zapojíte tři LED? Zvláštní – tři za sebou nebudou svítit vůbec, tři vedle sebe ano… Jak je to možné? Proč je v tom rozdíl? Přesně to se dozvíte v této kapitole.

[eknh.cz/lsp](https://eknh.cz/lsp)