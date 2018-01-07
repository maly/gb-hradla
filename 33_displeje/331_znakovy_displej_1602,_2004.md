## 33.1 Znakový displej 1602, 2004 {#33-1-znakov-displej-1602-2004}

Dobře známý je displej, pro který se vžilo označení 1602 – 16 znaků, 2 řádky. Určitě jste ho už někde viděli, a když ne tento, tak jeho většího bratříčka 2004 (20 znaků, 4 řádky).

![369-1.jpeg](images/00208.jpeg)

Vyrábí se v různých barevných provedeních, nejčastěji jako černé znaky na žlutozeleném pozadí, nebo jako bílé znaky na modrém pozadí, popř. modré na bílém pozadí. Tyto displeje obsahují řadič typu Hitachi HD44780, pro který existuje řada knihoven.

![369-2.jpeg](images/00358.jpeg)

Skvělé na těchto displejích je, že jsou velmi jednoduché na ovládání – stačí osmibitová datová sběrnice (DB0-DB7), několik řídicích signálů (RS, R/W, EN) a jeden potenciometr pro nastavení jasu (Vee).

Což se lehce napíše a hůř provede, protože Arduino zas tolik digitálních výstupů nemá, a každý přijde vhod. Naštěstí mají tyto displeje možnost pracovat ve čtyřbitovém režimu. Čtyři nižší bity se připojí k zemi, a komunikuje se pouze přes horní čtyři bity (D4-D7). Navíc lze vynechat i  řídicí vstup R/W, který říká, zda se z displeje čte (1), nebo do něj zapisuje (0), a napevno určit, že do řídicího obvodu displeje se bude jen zapisovat.

Pak už zbývá jen šest vodičů: čtyři datové, jeden povolovací (EN) a jeden, kterým se říká, jestli se posílá řídicí instrukce (RS=0), nebo znaky ke zobrazení na displeji (RS=1).

![370-1.png](images/000292.png)

Obvod je potřeba nejprve přepnout do čtyřbitové komunikace – pomocí sekvence speciálních příkazů. Jakmile je displej správně nastaven, stačí jen posílat ASCII kódy znaků, které se mají zobrazit, a posílat je po čtyřech bitech, nejprve vyšší, pak nižší. Pomocí některých řídicích kódů lze nastavit, kam se má další znak zapsat, popřípadě vytvořit několik vlastních znaků a používat je (symboly, znaky s diakritikou, …)

Arduino má naštěstí knihovnu, která se jmenuje LiquidCrystal, a ta se postará o vše potřebné.

A kromě knihovny vám může pomoci ještě jeden fígl – hledejte „1602 I2C expander“. Vypadá to nějak takto:

![371-1.jpeg](images/00346.jpeg)

Tento modul je uzpůsobený pro připojení k displeji 1602 nebo 2004\. Postará se o správné řízení datových i řídicích signálů, obsahuje trimr pro nastavení jasu, omezovací rezistor pro podsvícení, zkrátka vše, co je k těmto displejům potřeba. A to nejlepší nakonec: displej bude fungovat jako každá jiná periferie na sběrnici I2C! (A samozřejmě i pro tuto variantu existuje knihovna, LiquidCrystal_I2C).

![371-2.jpeg](images/00394.jpeg)

Schéma a zdrojový kód najdete na [eknh.cz/1602](https://eknh.cz/1602)