# Mask

A maszk adatok bevitelére és műveletek végrehajtására szolgál. A maszkot az utasítás-áttekintésben lévő utasításra való kattintással hívhatja le.

A jobb egérgombbal lehívható menüben lévő [Infó], ill. az [Infó] [Az ablakról] után a maszkinfóban különböző maszkinformációk kerülnek megjelenítésre, többek között a maszkszám, a hozzá tartozó változótáblázat keresőszava, valamint a név, jelentés és alias mezőknél azon mező főbevitelének a neve is, amin a kurzor van. Itt a rekord ID és sor ID is megjelenítésre kerül. Ezek az ID-k az adatbázisban lévő rekordok azonosító számai, nem a maszkon lévő rekord hivatkozási számai.

## Menüsor

A menüsorban egy sor menü található, pl. az "Utasítás" menü az utoljára lehívott utasításokkal, vagy az "Info" menü, ami megjeleníti többek között a rekord módosítás utolsó módosítási dátumát és feldolgozói azonosítóját. Almenükön keresztül parancsokat hajthat végre, melyek egy meghatározott mezőben való konkrét munkára vonatkoznak ([Szerkesztés] a következőkkel: [Visszavonás], [Kivágás], [Másolás], [Beillesztés, [Törlés] stb.). Az [Ablak] [Standard méret visszaállítása] menüparanccsal bármikor visszaállíthatjuk a maszk nagyságát az aktuálisan az alkalmazás által beállított nagyságra.

## Szimbólumsor

A menüsor alatti szimbólumsorban egy sor nyomógombot talál szöveggel és szimbólummal, egy legördülő ablakkal és a logóval, amikkel parancsokat és műveleteket hajthat végre egérkattintással. E nyomógombok funkciója általában az egész látható maszkra vonatkozik, és nem arra a mezőre, amit éppen szerkesztünk. Az [Extrák] [Beállítások]-ban az Ikonsorok regiszterben megjeleníttetheti a szimbólumcímet (Szimbólumcím megjelenítése) vagy csak magukat a szimbólumokat.

|Szimbólum|Jelentés|
|----|----|
|Mentés, Tovább|Ezzel a floppylemez szimbólummal rendelkező nyomógombbal elmenti egy rekord módosításait. Ha el akar menteni egy rekordot és még hiányoznak szükséges mezőbevitelek, akkor kap egy üzenetet. Egyidejűleg a kurzor abba a mezőbe kerül helyezésre, amiben végre kell hajtani a bevitelt. Az infosystemekben a zöld pipával rendelkező Tovább nyomógombon keresztül indul el a maszk utólagos szerkesztése. Ennél kiürülnek a mezők és újonnan végrehajthat beviteleket.|
|Elvetés|Ezzel a nyomógombbal elvetheti egy rekord téves módosításait. Utána a "Menti a módosításokat?" kérdést kapja.|
|Info Akció|Az Akció vagy Info nyomógombra való kattintással megnyit egy kiválasztást funkciókkal, amik tematikus összefüggésben állnak a maszkkal. A nyomógombok a maszk fejrészében és táblázatában állnak rendelkezésre.|
|Nyomtatás|Ezen a nyomógombon keresztül egy maszk fejrészéből (budruck változó) a Nyomtatás maszkot nyitja meg. Ott beállítások hajthatók végre és kiváltható a nyomtatási folyamat.|
|Home|Ezzel a nyomógombbal az utasítás-áttekintés az előtérbe kerül helyezésre. Ez a nyomógomb funkció az <F6> billentyűparancsnak felel meg.|
|Új|Ezzel a nyomógombbal elindítja egy rekord készítését. Ezután írja be az adatait a beviteli mezőkbe! Ha egy kitöltött maszkot hívott le és az Új-ra kattint, akkor csak a mezők program-saját előzetes kitöltései maradnak meg. Új rekordot a Másolás nyomógombbal is felvihet.|
|Másolás|Ezzel új ugyanolyan rekordokat készíthet a megnyitott rekordból, ami mintaként szolgál. Ha a maszkon a Másolás-ra kattint, akkor készül egy új maszk, ami annak adataival van kitöltve, azonban a másolt rekord hivatkozási száma törlésre kerül. A másolt maszk többi adata rendelkezésére áll a bevitelhez, ill. módosításhoz az új rekordhoz. A kiindulási maszk az addigi hivatkozási számával változatlanul megmarad.|
|Megjelenítés|Egy ezzel a nyomógombbal lehívott rekord összes mezője csak a megjelenítésre szolgál. A megnyitásnak ez a módja akkor kínálkozik, ha a rekordot nem akarja módosítani. Ezzel zárlatot is megakadályoz, ha a rekordot már egy másik felhasználó megnyitotta a Szerkesztés módban. Ha úgy döntött, hogy módosít egy "Megjelenítés"-sel lehívott rekordot, akkor kattintson a "Szerkesztés"-re! Ezt követően a beviteli mezők a hozzáférési jogainak megfelelően írhatók.|
|Szerkesztés|Ha lehívott egy üres maszkot, akkor a "Szerkesztés"-re való kattintás után megkapja az üres [Objektum kiválasztás]-t, amiben egy fájl, csoport vagy sablon kiválasztása és a Keresés indítása után kiadásra kerülnek a meglévő rekordok. A kijelölt rekord Átvétel-e után annak maszkján a hozzáférési jogai szerint beviteleket vagy módosításokat hajthat végre. Menjen a kurzorral arra a helyre, ahol módosításokat akar végrehajtani, és írja be azokat! Karakterek törléséhez jelölje ki a karaktersort és törölje ezt a következővel: <Del> vagy <Backspace>! Ezek a módosítások a mentéssel lépnek érvénybe.|
|Legördülő ablak|Ez a legördülő ablak tartalmazza az utoljára szerkesztett rekordok listáját hivatkozási számmal, keresőszóval és rövid leírással (objektum-történet). Ez a lista a lefelé mutató háromszögre való egérkattintással nyílik meg. Szortírozva van, a legaktuálisabb lehívás áll a legfelső helyen.|


## Funkciósor nyomógombokkal

Egy maszk funkciósora a standard alapcsomagban nyomógombokat tartalmaz. A nyomógombok programfunkciók gyors lehívására szolgálnak. Megtakarítják Önnek többek között az ismételt beviteleket, pl. pénznemekét, a különböző maszkmezőkbe. Alárendelt maszkokat is megnyithat, anélkül, hogy a nyitott maszkot el kellene hagynia. A nyomógombokat megtalálja az egyes regiszterekben a fejrészben vagy a maszk táblázati részében. A funkciósorban lévő járulékos elrendezés bizonyos funkciók lehívását könnyíti meg.

Ezeknek a nyomógomboknak a mennyisége a maszk típusa és egyedi igényekhez való testreszabása szerint változik. A funkciósor korlátozott szélessége miatt a nyomógomb feliratok néha rövidítve jelennek meg.

A funkciósor nyomógombjai egérkattintással vagy billentyűkombinációval működtethetők, mégpedig a <Ctrl> billentyűt a 0-9 számjegyek egyikével kombinálva. A számok egymásutánja a nyomógombok sorrendjét tükrözi balról jobbra, az 1 az egészen balra lévőt jelöli. A billentyűkombináció a nyomógomb egérrel való megérintésénél megjelenítésre kerül egy színes tooltip-ben (szövegbuborékban).

Továbbá léteznek nyomógombok maszk és táblázati funkciókhoz is. Ezek a maszk felületen vannak vagy a Táblázat menüben vannak megadva és onnan vagy a sornagyítón keresztül hívhatók le. A súgót ehhez ugyanúgy kapja meg, mint a mezőkhöz való súgót.

## Regisztersor

A regisztersorban láthatja a regisztereket a címeikkel, pl. "Általános", "Raktár" vagy "Beszerzés". Hogy mely regiszterek állnak a rendelkezésére, azt a munkatartomány és a felhasználói jogok határozzák meg.

## Státussor

Az ablak alsó peremén lévő státussorban különböző információkat talál, többek között a hivatkozási számét és a keresőszóét, valamint az adott árucikk megnevezését (bal oldal). Mindig megjelenítésre kerül az Ön azonosítója, a mandant neve, valamint a hozzá tartozó felhasználói szerver max. háromjegyű lehívói száma, ami segíti Önt annak felismerésében, hogy mely maszk mely folyamathoz tartozik.

Továbbá a státussorban megjelenik egy esetleges írásvédelem oka. Ezenkívül megjelenik egy utalás, amennyiben megpróbál egy írásvédett maszkmezőt módosítani.

## Sornagyító

A jobb egérgombbal lehívható menüben a Sornagyító kiválasztásával, vagy a táblázati sorban a bal egérgombra való dupla kattintással egy további ablakban megjelenik - ha létezik - a sornagyító. Ott megjelenítésre kerülnek a táblázati mezőhöz tartozó adatok és egyesével szerkeszthetők is. Emellett nyomógombokkal a sornagyítóból közvetlenül az előző vagy következő sorba válthat. Ha a sornagyítót a menüsorból a [Táblázat] [Sornagyító]-n keresztül hívja le, akkor az a táblázat első sorára vonatkozik. A sornagyítóban a státussorban pótlólag megjelenítésre kerül, hogy mely táblázati sorban szerepelnek a megjelenített adatok.

## Előző sor, Következő sor

Az ezekre a nyomógombokra való kattintással abból a sorból, amiben Ön a sornagyítóban van, az előző, ill. a következő sorba mehet anélkül, hogy vissza kellene térnie a táblázatba.

A feldolgozás bizonyos lépései a sornagyítóban billentyűkombinációkkal is végrehajthatók.

## Almaszkok

Az almaszkok a lehívott maszkok fejrészéből kerülnek lehívásra. Az almaszk funkciója hasonló a táblázatokban lévő sornagyítóéhoz: Kiegészítő információkat jelenít meg, és lehetővé teszi további bevitelek kitöltését. Az almaszkok tartalma a főmaszkkal kerül elmentésre.