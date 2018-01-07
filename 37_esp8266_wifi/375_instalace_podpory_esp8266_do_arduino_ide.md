## 37.5 Instalace podpory ESP8266 do Arduino IDE {#37-5-instalace-podpory-esp8266-do-arduino-ide}

1. Nainstalujte ovladače pro USBtoUART převodník, který je v kitech WeMos a jejich klonech – bývá to CH340.

2. V Arduino IDE vyberte z menu Soubor – Vlastnosti, a do pole „Správce dalších desek URL“ přidejte adresu [arduino.esp8266.com/stable/package_esp8266com_index.json](http://arduino.esp8266.com/stable/package_esp8266com_index.json) (Pokud tam už nějaké záznamy máte, přidejte tento a oddělte jej čárkou)

![402-4.png](images/000159.png)

3. V menu Nástroje – Vývojová deska vyberte Manažér desek

![403-1.png](images/000281.png)

4. Vyberte desku ESP8266 (můžete použít filtrovací pole nahoře)

![403-2.png](images/000179.png)

5. Po nainstalování vyberte desku WeMos D1 Mini

![404-1.png](images/000387.png)

Příklady jsou v sekci Příklady z knihoven, klíčové slovo ESP8266\. Dokumentaci naleznete na [esp8266.github.io/Arduino/versions/2.3.0/](http://esp8266.github.io/Arduino/versions/2.3.0/)