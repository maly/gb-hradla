## 24.5 Několik tipů k pamětem {#24-5-n-kolik-tip-k-pam-tem}

Pokud budete používat polovodičové paměti, hodí se vám pár tipů.

Tak například: ve světě pamětí a podobných specializovaných obvodů už většinou opustíme naši oblíbenou řadu 74xx a obvody TTL. Každý výrobce si vyrábí vlastní obvody v různých konfiguracích. Pro svoje konstrukce pravděpodobně nebudete používat třeba SDRAM a podobné ultramoderní kousky. S největší pravděpodobností sáhnete po sériových pamětech, které si představíme za chvilku. Ale kdybyste náhodou někdy stavěli něco se staršími procesory, tak si pamatujte:

PROM se dají stále sehnat, možná by šlo jimi nahradit složitější kombinační obvody, ale jednou naprogramovaná PROM se už moc opravit nedá. Jednodušší a lepší bude použít obvody GAL.

EPROM jsou už hodně výběhové paměti. Můžete je sehnat ve výprodejích, ale počítejte s tím, že nemusí fungovat, a taky s tím, že pro jejich mazání potřebujete ultrafialovou výbojku.

EEPROM jsou lepší volba, už jen proto, že se stále vyrábějí. Pro amatérské konstrukce jsou vhodné typy 28C64 (8k × 8), 28C256 (32k × 8) a 28C010 (128k × 8). Všechny tyto typy se vyrábějí i v pouzdrech DIP.

FLASH jsou vyráběny v řadě 39F – např. 39F010 (39SF010 – S označuje standardní napájení 5 V, L nízké 3,3 V) s kapacitou 128k × 8, 39F020 a 39F040 (256k × 8 a 512k × 8).

Paměti SRAM si výrobci značí ledasjak, ale vždy lze najít alternativu. Jen je potřeba spíš sledovat parametry, než hledat nějakou logiku v číslování. Oblíbené paměti jsou např. 6264 (8k × 8), 62256 (32k × 8) a pak 128k × 8 (např. AS6C1008), 256k × 8 (AS6C2008) a 512k × 8 (AS6C4008)

Ve starých PC AT se daly najít rychlé cache paměti SRAM, většinou organizované jako 32k × 8 apod. Jejich výhodou byla velká rychlost, nevýhodou velká spotřeba.

Zajímavé jsou takzvané „dual port“ paměti. Mají dvě sady adresních, datových i řídicích vývodů, takže se tváří jako dvě paměti, ovšem sdílejí společnou paměťovou strukturu. Používají se například jako video RAM – z jedné strany k nim může přistupovat procesor a zapisovat, a z druhé strany může nezávisle videoprocesor číst a zobrazovat data.