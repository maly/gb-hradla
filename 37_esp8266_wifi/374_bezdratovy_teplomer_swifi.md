## 37.4 Bezdrátový teploměr s WiFi {#37-4-bezdr-tov-teplom-r-s-wifi}

Tentokrát opustíme bezpečný svět Arduina UNO a použijeme výše zmíněný modul WeMos D1 Mini spolu s moduly BMP180 (ten už známe) a SHT30 – tento modul měří teplotu a relativní vlhkost a připojuje se přes sběrnici I2C. Modul SHT30 je o něco přesnější než DHT11/DHT22, ale především používá standardní sběrnici I2C.

![402-1.jpeg](../images/00209.jpeg)![402-2.jpeg](../images/00134.jpeg)![402-3.jpeg](../images/00200.jpeg)

Poskládání takového teploměru je otázka několika minut, napsání softwaru také. Naštěstí existuje způsob, jak takovouto sestavu přímo programovat přes Arduino. Dovolte odbočku:
