## 38.1 Solární články {#38-1-sol-rn-l-nky}

Boom solárních elektráren přinesl kromě negativních dopadů i některé pozitivní, a jedním z nich je výrazné zlevnění solárních – přesněji fotovoltaických – článků. Se zařízeními „na sluneční baterie“ se můžete setkat v nejrůznějších situacích, od smysluplných (napájení inteligentních autobusových zastávek nebo autonomních komunikačních zařízeních v místech, kam nelze moc dobře dovést elektřinu) až po samoúčelné, a někdy i vysloveně podivné. Díky rapidnímu poklesu cen si můžete i poměrně výkonné a velké fotovoltaické panely pořídit za ceny v řádech desítek korun.

Fotovoltaické články jsou v podstatě velkoplošné polovodičové diody, kde vlivem energie zvenčí vzniká elektrické napětí. Vzpomeňte si na jeden z prvních experimentů v této knize, kdy jste svítili na LED jasným světlem a měřili vznikající napětí. Tak fotovoltaický článek je založený na stejném principu, jen na větší ploše.

Nevýhodou FV článků je poměrně malá účinnost – u těch, které za levno koupíte, to bude v jednotkách procent, průmyslové mívají okolo 15 %, experimentální laboratorní články dosahují účinnosti 30-40 procent. Ale i tak lze malé solární panely použít k napájení low power zařízení.

Fotovoltaický článek funguje vlastně jako baterie – má kladný a záporný pól, a když na něj dopadá světlo, tvoří se mezi nimi napětí. Problém je, že účinnost záleží i na dalších faktorech, jako je úhel dopadajícího světla nebo teplota článku. Pokud vás třeba napadlo zvýšit účinnost tím, že před článek předřadíte lupu, která koncentruje větší množství dopadajícího světla, je to nápad v zásadě dobrý, ale myslete na to, že spolu se slunečním svitem koncentruje čočka i teplo, a článek se snadno přehřeje, popřípadě spálí.

Napájení z fotovoltaických článků vyžaduje trochu víc přemýšlení, než jen: semhle plus, semhle mínus… Intenzita světla, a tedy i množství dodané energie, kolísá v průběhu dne – vlivem oblačnosti, nebo i vlivem toho, jak Slunce putuje po obloze a světlo tak dopadá z různých úhlů (samozřejmě je možnost vybavit solární panel zařízením, které jej bude natáčet podle směru svitu, ale to spotřebuje rovněž nějakou energii…) Navíc v noci nebude produkovat fotovoltaický článek téměř žádnou energii, protože v noci bývá většinou v našich zeměpisných šířkách tma.

Proto je dobré za FV článek zapojit nějaké zařízení, které dokáže jímat vyrobenou energii – například NiMH baterii (přes Schottkyho diodu, aby proud netekl zpátky do článků), Li-Ion baterii (přes specializované moduly, určené k nabíjení takových baterií), nebo takzvaný Supercap (superkondenzátor, anglicky supercapacitor, s kapacitami v desítkách až stovkách Faradů).

Pozor na Li-Ion baterie – například oblíbeného typu 18650! Mají sice velkou kapacitu a spoustu dalších dobrých vlastností, ale jsou velmi citlivé na správné zacházení a na přesné nabíjení specifikovaným napětím a proudem. Pokud překročíte povolená nabíjecí napětí a proudy, začnou v bateriích probíhat chemické reakce, které mohou vyústit až ve zničení článku, popřípadě k jeho prasknutí, požáru a explozi – navíc lithium a jeho sloučeniny jsou poměrně agresivní.

##### 39 Sigfox {#39-sigfox}
