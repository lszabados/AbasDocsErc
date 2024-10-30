# Diszpozíció

A diszpozíció az anyagtervezést és a határidő-tervezést hajtja végre.

A diszpozícióval arról gondoskodunk, hogy mindig elegendő anyag és gyártási kapacitás álljon rendelkezésre a vevői megrendelések határidőn belüli lebonyolításához. E célból a diszpó rendelési és gyártási javaslatokat készít, anyag és kapacitás foglalásokat hajt végre, és javaslatokat tesz a határidőkre a vevői megrendelések lebonyolításához. Ezeket a javaslatokat és foglalásokat egy sor lista és táblázat mutatja meg. Ezek átláthatóvá teszik a diszpozíció eredményeit, és utalnak az inkonzisztenciákra és az esetlegesen szükséges határidő eltolódásokra.

Az anyag- és határidő-tervezés egy változás-számításon (Net-Change-eljárás) alapul: Tehát nem számolja át minden egyes futtatáskor az egész vevői megrendelés és szállítói megrendelés készletet, hanem csak azt, ami az utolsó diszpófuttatás óta módosult (új bevétek, stornózások, mennyiség vagy határidő változások).

## Fogalmak

|Fogalom|	Jelentés|
|---|---|
|Beszerzések|	Rendelési javaslatok, átraktározási javaslatok, gyártási javaslatok, jóváhagyott gyártási javaslatok, megrendelés tételek más cégtől való beszerzésekhez és átraktározásokhoz|
|Beszerzések, változó|	Beszerzési javaslatok, amiknél a Folyamat fixálása mező üres. A diszpó módosíthatja a mennyiségeket, határidőket és felhasználásokat, törölheti a fölösleges változó beszerzéseket.|
|Beszerzések, fix|	Beszerzési javaslatok, amiknél a Folyamat fixálása mező ki van jelölve, és a már jóváhagyott beszerzések. A diszpó nem módosíthatja a mennyiségeket, határidőket és felhasználásokat, nem törölheti a fölösleges fix beszerzéseket.|
|Foglalások| Nyersanyag-, gyártóeszköz-, művelet-foglalások (kapacitás-foglalások); A foglalások az archivált beszerzési folyamatokhoz ugyancsak az irattárba kerülnek.|
|Foglalások, változó|	A minimális készlet feltöltéséhez szükséges mennyiség, foglalások a megrendelés tételekhez, amiknél a Folyamat fixálása mező üres, valamint foglalások azokhoz a beszerzésekhez, amik csak változó foglalásokat szolgálnak ki (a "Legkésőbbi befejezési határidő" mező üres). Ha ilyen foglalásokhoz anyagot kell beszerezni, akkor a program ezeket csak az utolsó kritikus beszerzés utánra tervezi be.|
|Foglalások, fix|	Foglalások azokhoz a megrendelés tételekhez, amiknél a Folyamat fixálása mező ki van jelölve, valamint azokhoz a beszerzésekhez, amik (szintén) fix foglalásokat szolgálnak ki (a legkésőbbi befejezési határidő egybeesik a szükséglet határidővel). Ha ilyen foglalásokhoz anyagot kell beszerezni, akkor a program megkísérli időben fedezni az igényeket.|
|Beszerzések/foglalások, vevői megrendelésre vonatkozó|	Beszerzések és foglalások változatra vagy vevői megrendelésre vonatkozó diszpozícióval, amiknél a Felhasználás mező ki van töltve.|
|Beszerzések/foglalások, raktárra vonatkozó|	Beszerzések vagy foglalások szükségletre, minimum készletre vagy maradék mennyiségre vonatkozó diszpómóddal vagy bevitel nélkül a megfelelő mezőben.|
|Beszerzési utalás|	Lehetőség van beavatkozásra, hogy befolyásolhassa a már létező beszerzések és az anyagfoglalások közötti hozzárendelést.|
|Határidők|	Ezek definíciói egy külön fejezetben kerülnek tárgyalásra.|
|Kritikus azonosító|	Csak kritikus javaslatok, Határidő kritikus, S/Státus, Előd kritikus, Nem kritikus|

### Kritikus fogalom további magyarázata

Egy ügylet akkor kritikus, ha a legkorábbi befejezési idő egybeesik a tény befejezési idővel vagy később van, ill. a kezdési idő a múltban van vagy a napi dátummal rendelkezik. Így a megbízás nem intézhető el. Egy ilyen bevitelt a diszpozíció a megnevezett mezőkben hajt végre.

Ha a Kritikus mezők ki vannak jelölve, pl. kiválasztási kritériumként infosystemekben, akkor a táblázatban ezekkel a jellemzőkkel kerülnek megjelenítésre rekordok - folyamatok, foglalások, beszerzések stb.

A Beszerzési állapot infosystemben láthatja, hogy hol vannak a kritikus ügyletek okai. A Tűrés-en keresztül tovább korlátozhatja a figyelembe veendő ügyleteket. Ha a mező üres, akkor a nem kritikus ügyletek is megjelenítésre kerülnek a táblázatban.

Hogy beállítsa a beszerzési és értékesítési nyitott szállításokra érvényes paramétereket a Kritikus-értékeléshez, a FE.PAR fájl áll a rendelkezésére.

A Kritikus státus szövegben, szimbólumokban és színekben kerül megjelenítésre.

|Szín vagy szimbólum|Jelentés|
|---|---|
|Piros, csillag (*), A folyamat kritikus|Az ügylet, a foglalás, beszerzés stb. határideje kritikus. A tervlapon és a 10022 Beszerzési állapot infosystemben a piros a következőt jelenti: a foglalás vagy a múltban van vagy kritikus, mivel kritikus egy beszerzés, ami ezt a foglalást kiszolgálja.|
|Sárga, hajlított ékezet (^). A folyamat kritikus szakaszban van|Egy előző igény, foglalás, beszerzés stb. kritikus. A tervlapon és a 10022 Beszerzési állapot infosystemben a sárga a következőt jelenti: a foglalás a jövőben van és kritikus, mivel az elődje a gyártási listában kritikus.|
|Zöld, aláhúzás (_). A folyamat nem kritikus|A tétel, foglalás, beszerzés stb. nem kritikus|
|Üres|Nem ellenőrzött folyamat.|

## Diszpozíció futtatása

A diszpozíció futtatása lehet folyamatos (ütemezésen keresztül pl 10 percenként vagy naponta) és lehet manuális.

Alapértelmezetten éjjel egyszer lefut.

Amikor pl. vevői megbízást rögzítünk, gyártási javaslatok vagy beszerzési javaslatok addig nem keletkeznek, amíg a Dispo nem fut le. Ezért, ha szeretnénk a megbízás rögzítése után azonnal ilyen információkat látni, kézzel kell a Dispo futását elindítani.

### Dispo kézi futtatása

A Standard/Diszpozíció/Diszpozíció indítása menüponttal lehet.

> A Dispo lefutása után, kaphatjuk azt az információt, hogy nem teljes. Ez amiatt lehet, hogy egyes szerkesztés alatt lévő adatokat a dispo nem tudja kiértékelni.