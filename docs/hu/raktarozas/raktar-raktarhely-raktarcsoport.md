# Raktár, Raktárhely, Raktárcsoport

## Raktárcsoport

### Belső raktárcsoport

Van egy raktárcsoport, ami a belső raktárakat összefogja: a belső raktárcsoport (helyszíni raktárcsoport). Ennek az [Üzemi adatok megjelenítésé]-ben a Belső raktárcsoport mezőben kell beírva lennie. Az összes többi raktárcsoport külső raktárt ír le.

> A belső raktárcsoport egyszer kerül meghatározásra és már nem módosítható.

### Külső raktárcsoport

A külső raktárcsoportok különböző folyamatokat képezhetnek le. Ennél a külső nem szükségszerűen földrajzi elkülönítést jelent a belső raktárcsoporttól. A készletek és beszerzések elkülönítésén keresztül, amiket a diszpozíció raktárcsoportonként vesz figyelembe, külön kezelhetők készletek. Így pl. elkülöníthető egy pótalkatrész raktár, amit mindig elegendő mennyiséggel kellene feltölteni, az újonnan gyártott cikkektől. Egy belső logisztika is leképezhető több raktárcsoporton keresztül. A megfelelő raktárcsoport tulajdonságokkal egy árucikk így átraktározási javaslatok segítségével az árubeérkezést követően a magasraktárba kerülhet, onnan pedig tovább egy gyártási raktárhelyre, ha ott szükséglet (igény) keletkezik. A külső raktárcsoportok különösen hasznosak a szállítóknál lévő külső raktárakként a biztosított anyag folyamatokhoz. Biztosított anyaggal egy más cégtől beszerzett cikk beszerzési megrendelése ekkor kivált egy átraktározási javaslatot a biztosított anyaghoz a szállítóban beírt konszignációs raktárhelyen keresztül. Az átraktározási javaslat pedig létrehozza a kezdeti beszerzést a belső raktárcsoportban a biztosított anyaghoz, a beszerzési módtól függően.

A raktárhelynek az objektumokban való megadása a raktárhely raktárhoz való egyértelmű hozzárendelésén keresztül mindig magában foglalja a hozzá tartozó raktárcsoportot is.

Ennél biztosítani kell, hogy az értékesítési foglalásokhoz ugyanaz a raktárcsoport legyen hozzárendelve, mint az értékesítési tételekhez, és a gyártási vagy beszerzési cikkek darabjegyzék tételei ugyanazzal a raktárcsoporttal rendelkezzenek, mint a gyártási javaslatok, ill. beszerzési tételek.

## Raktár

A raktár a raktárstruktúra közbenső szintjét jelenti a diszpóreleváns raktárcsoport és az egyes raktárhelyek között. Raktár szinten csak a kiszerelésköteles egységenkénti össszkészletek kerülnek megkülönböztetésre. Az olyan tulajdonságok, mint pl. sarzs, felhasználás vagy projekt, a raktár szinten nem kerülnek rögzítésre.

A raktárhellyel ellentétben a raktáraknak lehet címük és telefonszámuk. Mivel az anyagokat raktárhely nélkül nem lehet könyvelni, és a raktárhelyet mindig raktárhoz kell rendelni, az abas-ban minimum egy raktárra és raktárhelyre szükség van.

Raktárakat és raktárhelyeket akkor törölhet, ha még nincsenek könyvelve, vagy ha előzőleg az összes készlet kivételezésre került. Ez az utasítás-áttekintésben a következőn keresztül történik: Különböző utasítások-Törlés-Raktár, ill. Raktárhely. Ha töröl egy raktárt, ill. raktárhelyet, akkor a program azokat az irattárba teszi. Ha ezután könyvel egy törölt raktárhelyet, pl. a Szállítólevelek könyvelése utasítással, akkor újra aktívvá válik. Noha egy raktár nem könyvelhető közvetlenül, de szintén újra aktiválódik, mihelyt könyvel egy raktárhelyet ebben a raktárban.

## Raktárhely

A Raktárhely a legalacsonyabb szintet jelenti a raktárhierarchiában. Minden egyes raktárkönyvelésnek szüksége van egy raktárhely megadására. Minden egyes raktárhely egyértelműen kiosztott keresőszaván keresztül az árucikk raktárhely készletek bármikor ismét hozzáférhetők. Ezen a szinten az árucikk készletek közvetlenül össze vannak kapcsolva. Ezek a raktárhely készletek jelentik a többi raktárszint összes összeadott készletének az alapját. A raktárhelyen az összes kiszerelési egység releváns, amit egy árucikk felvehet.

A Raktárhely maszkon a raktárhelyek adatai kerülnek kezelésre. Ha a raktárhelyek nincsenek könyvelve, akkor törölheti őket. Ha a raktárhelynél a raktárcsoport standard bevételezési raktárhelyéről, ill. standard kiadási raktárhelyéről van szó, akkor helyette egy másik raktárhelyet kell beírni standard raktárhelyként. Ha egy raktárcsoport teljes struktúrája törlésre kerüljön, akkor először a raktárcsoportot kell törölni, mielőtt törölni lehetne a standard raktárhelyet. Először törölje a raktárcsoport összes raktárhelyét, ami nem standard raktárhely, utána az összes raktárt, végül pedig a raktárcsoportot! Ezáltal megszűnik a standard raktárhelyként való megjelölés és ez a raktárhely is törölhető.

