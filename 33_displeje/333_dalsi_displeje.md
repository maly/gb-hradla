## 33.3 Další displeje {#33-3-dal-displeje}

Před lety se objevily ve výprodejích velmi levné displeje z mobilních telefonů, například ze starých Nokií 5110 atd. Tyto displeje mívají vlastní řídicí obvod, s nímž se komunikuje buď přes SPI, nebo po I2C. Nadšenci začali tyto displeje připojovat k jednočipům, protože byly levné a snadno řiditelné. Dnes je k dispozici velké množství modulů s takovými displeji, většinou za pár desítek korun (v českých e-shopech za jednotky stokorun), a se širokou škálou možností – s různým rozlišením, s různým rozhraním, barevné i monochromatické, LCD i OLED, někdy i s dotykovou vrstvou… Často je na stejném modulu například i slot pro SD kartu se SPI rozhraním.

![373-1.jpeg](images/00133.jpeg)

K těmto displejům je vždy třeba přistupovat opatrně. Naprostý „noname“ bude asi těžké oživit, pokud nevíte, jaký řídicí obvod používají. Nejjistější je držet se takových, pro které si najdete dostatek literatury, a nejlépe hotových knihoven. Mohu doporučit hledat displeje s řadiči ILI9340 a ILI9341, pro ně je dostatek knihoven, jak pro ovládání, tak i pro kreslení grafických prvků, psaní znaků atd.