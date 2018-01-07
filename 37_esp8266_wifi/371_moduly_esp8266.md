## 37.1 Moduly ESP8266 {#37-1-moduly-esp8266}

Moduly s tímto obvodem se brzy objevily v několika variantách. První byl modul, dnes označovaný jako ESP-01, připojovaný přes osm pinů:

![396-1.png](images/000401.png)

ESP-01 byl nejjednodušší, nejlevnější a používal se především jako periferie – připojuje se přes sériové rozhraní (většinou rychlostí 115200 Bd) a veškerá komunikace s internetem se odehrává pomocí speciálních příkazů („AT příkazy“).

Například když pošlete do ESP8266 sekvenci znaků „AT+CWLAP\n“ (bez uvozovek, velká písmena), oscannuje si dostupné WiFi sítě a vrátí seznam jejich identifikátorů.

K WiFi síti se připojíte pomocí AT+CWJAP = „moje-sit“,„moje-heslo“

Po úspěšném připojení k WiFi AP můžete zkusit navázat spojení se serverem: AT+CIPSTART = „TCP“,„192.168.0.1“,„80“

Pak můžete přenášet data: AT+CIPSEND = délka dat, a samotná data…

Naštěstí není potřeba používat tento způsob, existují knihovny, které AT příkazy zapouzdřují a navenek dovolují pohodlnou práci pomocí funkcí vyšší úrovně.

Připojení tohoto modulu přímo k Arduinu nedoporučuju – modul je určen pro napětí 3,3 voltů, a snadno jej spálíte. Použijte buď převodník úrovní, nebo specializovaný shield s tímto modulem, kde je převodník už zabudovaný.