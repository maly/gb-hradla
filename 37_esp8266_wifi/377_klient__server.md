## 37.7 Klient / server? {#37-7-klient-server}

Zásadní otázka u našeho teploměru je: Klient, nebo server? Odpověď záleží na tom, jestli:

• chcete data nějak zpracovávat, třeba na serveru

• máte dostatek volných WiFi kanálů, tedy bydlíte někde na samotě

• se chcete jen lokálně podívat, třeba z mobilu, kolik je stupňů.

Pokud pro vás platí poslední případ, a zároveň nejste někde v hustě osídlené oblasti se spoustou aktivních WiFi, zvolte způsob „server“. Naprogramujte ESP8266 jako server, napište jednoduchou webovou stránku a v ní aktualizujte hodnoty teploty, vlhkosti a tlaku. Pak se k takovému teploměru připojíte jako k libovolnému access pointu a pomocí prohlížeče sledujete data.

V opačných případech zvolte postup „client“. Ovšem znamená to, že někde (u vás doma, v routeru, v domácím serveru, nebo v internetu kdesi) musí běžet server, k němuž se teploměr bude pravidelně připojovat a hlásit naměřené údaje. Do podrobností se tu nebudu pouštět, to záleží asi na vkusu každého z vás, jaké řešení zvolí.

Existují služby (asi nejznámější je Thingspeak), které po registraci nabízejí jednoduché serverové API pro zasílání hodnot. Na webu můžete data prohlížet, zobrazovat v grafech, nebo exportovat pro další zpracování.

Další možností je vlastní server, buď s HTTP REST API, nebo (lépe) s MQTT brokerem. MQTT je de facto standard pro posílání zpráv ve světě Internetu věcí (IoT). Jde o jednoduchý a datově nenáročný protokol pro posílání zpráv a jejich přijímání, založený na architektuře pub-sub (Publisher – Subscriber). Podrobnější popis je mimo záběr této knihy, zájemce odkážu například na svůj web Iotta.cz, kde se MQTT věnuji.

Schéma a zdrojový kód najdete na [eknh.cz/esp](https://eknh.cz/esp).

##### 38 Low Power {#38-low-power}