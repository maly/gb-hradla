## 37.6 WiFi Manager {#37-6-wifi-manager}

Podpora pro WiFi je u desek D1 Mini v prostředí Arduino naprosto excelentní. Stačí zadat jméno WiFi sítě, heslo, připojit se… Jenže co když nechcete nechávat heslo ke své wifi síti v kódu, nebo budete instalovat zařízení někde, kde je síť, ke které zatím nemáte údaje? Snadná pomoc, použijte skvělou knihovnu WiFi Manager ([github.com/tzapu/WiFiManager](https://github.com/tzapu/WiFiManager))

Tato knihovna nabízí, mimo jiné, funkci autoConnect(ssid); Při prvním zapnutí se ESP8266 zapne jako access point, a vy se k němu můžete připojit jako k jakémukoli jinému access pointu – třeba přes smartfon. Pak stačí otevřít prohlížeč a zadat adresu 192.168.4.1 a otevře se stránka s nastavením wifi manageru, kde nastavíte jméno sítě a heslo. Po úspěšném nastavení si WiFiManager tyto údaje uloží k dalšímu použití, a celé zařízení restartuje.

Pokud knihovna po startu objeví uložené údaje, zkusí se k takové síti připojit, už jako klient. Uspěje-li, spustí se hlavní program. Neuspěje-li, opět se přepne do AP módu a funguje jako server s nastavovací stránkou.