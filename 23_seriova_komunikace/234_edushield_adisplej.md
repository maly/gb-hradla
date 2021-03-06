## 23.4 EduShield a displej {#23-4-edushield-a-displej}

EduShield obsahuje rovnou dvě zařízení, připojená na sběrnici I2C. Jedno z nich jsou hodiny reálného času DS1307 – k nim se za chvíli dostaneme. Druhé zařízení je budič sedmisegmentového displeje. Jestli se ptáte, jaký to je typ, že byste si to našli v datasheetech, tak vás musím rovnou upozornit, že neuspějete – místo konkrétního obvodu je tam naprogramovaný _jednočip_ ATtiny2313, který funguje jako I2C slave. Poslouchá na adrese 0x27 a jediné, co s ním můžete dělat, je zapsat jeden byte do jedné z adres 0, 1, 2, 3.

Komunikační protokol je extrémně jednoduchý: pošlete dva bajty. První je adresa (0 – 3) která zároveň odpovídá pozici na displeji (0 vlevo, 3 vpravo). Druhý je bajt, který říká, co má na dané pozici svítit. Není použitý žádný kód, žádné sofistikované převody, jednotlivé bity zkrátka říkají, jaké segmenty mají svítit. Nejvyšší bit je desetinná tečka, nejnižší segment A. Tedy hodnota 0x00 celou pozici zhasne, hodnota 0x7F rozsvítí všech sedm segmentů („osmička“), hodnota 0xFF udělá totéž i s desetinnou tečkou, hodnota 0x06 rozsvítí segmenty B a C (a ty dohromady dají znak „jednička“)…

Schéma a zdrojový kód najdete na [eknh.cz/edudis](https://eknh.cz/edudis).
