# Helyettesítő karakteres keresés

Ha nem biztos benne, hogy a "Bachmaier" vevőt "ai"-val vagy "ei"-vel vagy "ey"-vel írják-e, akkor a helyettesítő karakterrel szótöredékeken keresztül kereshet. Ennek előfeltétele, hogy a [Konfiguráció megjelenítésé]-ben operátorként helyettesítő karakter legyen beállítva.

> A helyettesítő karakteren keresztüli szelekció csak szövegmezőkben, keresőszavakban és hivatkozási számokban lévő tartalmakhoz lehetséges.

A helyettesítő karakterrel való kereséshez írja a név vagy a fogalom ismert töredékét a keresési kritériumok mezőjébe! Utána adjon hozzá egy karaktert, ami úgynevezett jokerként helyettesíti a hiányzó betűket, pl.:

|Jel|Magyarázat|
|---|---|
|Kérdőjel (?)|Tetszőleges karakter|
|Csillag (*)|Tetszőleges karaktersor, szóköz is|
|(a-e)|Minden karakter "a"-tól "e"-ig abc sorrendben (azaz a, b, c, d, e)|
|/abc/|Minden, a két perjel között megadott karakter (itt:: a, b, c)|
|Hajlított ékezet (^)|Mező vége vagy mező eleje|
|Aláhúzás ( _ )|Tagadja az utána bevitt feltételt|
|Visszaperjel (\)|A karakter a visszaperjel után mint Escape karakter a keresőmintán belül nem kerül értelmezésre, hanem úgy kerül keresésre, ahogy be van írva|


|Jel|Magyarázat|
|---|---|
|<?>|Tetszőleges karakter hegyes zárójelben|
|<*>|Tetszőleges szöveg hegyes zárójelben|
|(A-Z)|A következő nagybetű|
|/Kk/ezd|A "Kezd" és "kezd" karaktersorok|
|/.,!?/|Minden megadott írásjel|
|-^|Kötőjel a mező végén, pl. elválasztási helyek|
|^(0-9)|Számjegy a mező elején|
|<-#>|Tetszőleges hosszúságú nyíl a "<----->" formában|
|_ (A-Z)|Nagybetűk, amik előtt nincs szóköz|

A keresési mintákat a program a helyes bevitel szempontjából ellenőrzi. Így pl. a zárójeleknek és perjeleknek mindig kétszer kell rendelkezésre állniuk. Az aláhúzást ( _ ) követnie kell egy karakternek, amire vonatkozik.

Egy tartomány keresése a következő bevitelen keresztül történik: "Alsó határ!Felső határ", ahol a felkiáltójel "ig"-nek kerül olvasásra. Ha a határok számokkal kezdődnek, akkor a program a határok közötti összes hivatkozási számot kiválasztja. Ha a határok betűkkel kezdődnek, akkor a program a határok közötti összes keresőszót választja ki.

|Jel|Magyarázat|
|---|---|
|B!E|B az alsó, E a felső határ; megkeresi az összes rekordot B-vel, C-vel, D-vel és E-vel|
|!|felső és alsó határ nélkül; az összes rekordot a hivatkozási szám sorrendjében keresi (nem a keresőszó sorrendjében, mivel nincs megadva betű)|
|B!|felső határ nélkül; az összes rekordot a keresőszavak sorrendjében keresi, B-től a lista végéig|
|!E|alsó határ nélkül; az összes rekordot keresi a lista elejétől az E-ig (azaz A-tól E-ig)|

A helyettesítő karakter továbbá lehetőséget kínál betűtartományok célzott keresésére.



|Jel|Magyarázat|
|---|---|
|a(b-e)f|megtalálja az összes rekordot abf-fel, acf-fel, adf-fel, aef-fel|
|a/bc/d|megtalálja az összes abd és acd rekordot|
