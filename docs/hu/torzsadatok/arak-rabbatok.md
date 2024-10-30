# Árak rabbatok

Az árak-rabbatok egy külön adatbázis az ABAS-on belül, ami árlisták karbantartását tesziu lhetővé.

Ehhez az ABAS biztosít egy Árak Rabbatok adatbázist és infosystemeket a karbantartáshoz.

## Vevő/szállító árcsoport

Minden vevőnél és szállítónál megadható 1 árcsoport. Az adott vevő/szállító ebbe a csoportba tartozik.

![alt text](image-2.png)

Fontos, az árlistát nem a vevő vagy szállító neve vagy kódja hastározza meg, hanem a beállított árcsoport.

Ez bármi lehet, de alapból a vevő keresőszava vagy number értéke.

Ez a megoldás azért jó, mert ha van pl egy szállítónk, akinek franchise üzletlánccal rendelkezik. 5 külön adószámmal rendelkező üzled, de mégis ugyan az. Egy áron dolgoznak. Elegendő egy árlista, csak az árcsoportot azonosra állítjuk és kész.

## Árucikk árcsoport

Hasonló az elv a Vevő/szállító árcsoporthoz.

A lényeges különbség, hogy az árucikkhez tartozik egy értékesítési árcsoport, valamint a beszerzés oldalon minden szállítóhoz egy beszerzési árcsoport.

![alt text](image-1.png)

![alt text](image.png)

Az egészet megfejeli, hogy amennyiben vannak külső raktárcsoportok, ott külső raktárcsoportonként lehetséges 5-5 szállító, mindnek lehet 5-5 beszerzési árcsoportja. (Értékesítési árcsoport nincs a külső raktárcsoporton!)

> alapesetben raktárcsoporton belül egyforma árcsoportot szokás beállítani, rika, ha ettől el kell térni.

## Árak rabbatok fő oldal

![alt text](image-3.png)

Keresőszónak rendszerint a vevő kódját vagy árcsoportját írjuk. így egy árlista minde elem, ugyanazon néven fut.
Keresés megkönnyítésére a megnevezésnél írjuk be az árucikk nevét

Nagyon fontos a típus. Értékesítési árlista vagy beszerezési árlista.

Ezt követi 3 alapvető érték:
1. dátum. Mikortól és meddig érvényes az árlista.
2. Árucikk árcsoport
3. Vevő/Szállító árcsoport

Az a 3 alapvető érték, hogy az árlista kiválasztásra kerül e.
Ha egy megbízásnál a kiválasztptt vevő árcsoportja megegyezik az itt megadotal, akkor a vevőre érvényes az árlista.
Megbízás esetén értékesítési árlistának kell elnnie.
Ha a megbízáson szereplő árucikk árcsoportja megegyezik az itt megadott árucikk árcsoporttal, akkor az árucikkre érvényes az árlista
Az aktuális dátumnak a megadott intervallumba kell esnie.

### Hiányos adatok és hatásuk

Sem a dátumot, sem az árcsoport mezőket nem kell kitölteni. Mi történi, ha valami nincs megadva.

- ha a dátum üres, akkor minden időpontban érvényes az árlista. 
- ha a dátum tól értéke üres, akkor bármikortól érvényes
- ha a dátum ig értéke üres, akkor az árlista bármeggig érvényes
- ha a vevő/szállító árcsoport üres, akkor minden vevőre/szállítóra érvényes
- ha az árucikk árcsoport üres, akkor minden árucikkre érvényes.

### Több érvényes találat

Abban az esetben, ha több érvényes árlistánk is van, akkor a pontosabb vagy szűkebb értelmezés az elsődleges.
pl. Van egy árunk ahol a dátum nincs kitöltve, vagyis az ár mindíg érvényes.
Ha másik ár is van, de ott a dátum is ki van töltve és a dátumok között vagyunk, akkor ez az ár lesz az érvényes.

> Rossz példa: Ha felveszünk egy árat és nem adunk meg sem Cikk árcsoportot és Vevő/Szállítóárcsoportot és dátumot sem, akkor az abas elfogadja. Ilyen beállítással viszont mindenre amire nincs ár felvéve, vagy valami miatt nem érvényes, ezt az árat adja az ABAS, ami természetesen hibás működéshez vezet.

### Árak rabbatok a cikktörzsben

E.R.C. fejleszés az árucikk mask menüsorában A "New Price" gomb.

![alt text](image-4.png)

A gombra kattintva egy új Árak/rabbatok maskot nyit a rendszer beszerzési árlistának.
Árucik árcsoportot és a belső megnevezést kitölti, a többi adatot nem, hiszen ahhoz a vevőt/szállítót is ismerni kellene.

### Árak rabbatok a megrendelésekben

Amikor a beszerzési megrendelést készítünk, az ABAS a meglévő árlistából kikeresi a mennyiséghez érvényes árat. Ha ez nem jó és átírjuk, akkor automatikusan az aktuális árak/rabbatok mask-ot feldobja a rendszer, hogy javíthassuk az új érvényes árra, vagy észrevegyük, hogy az ár eltér a hivatalostól.

Ha nem volt ár, akkor egy új maskot dob fel a rendszer, hogy elmenthessük a megadott árat az árlistába.

> Természetesen nem kötelező javítani, ez egy lehetőség, és könnyítés, hogy nem kell külön kikeresni.

![alt text](image-5.png)

### Árak rabbatok a megbízásokban

Az eladáskor ugyan az a szisztéma, mint a beszerzéskor, ha a hivatalos árlistától eltér az ár, akkor automatikusan feldobja a rendszer az Árak /Rabbatok maskot.

## Árak/Rabbatok rendszerben az Árak frissítése

A törzsadatok/Árak-Rabbatok alatt a "Ár és rabatt karbantartás" infosystemet kell elindítani.

Az infoszsystemmel egyszrre több sor árat tudunk javítani. Pl. Szűrönk egy Vevő/Szállító árcsoportra és a szállítótól kapott árlista alapján javíthatjuk az árakat.

Két módszerrel lehet új árat megadni:

1. A meglévő árlista felülírása. Ezt akkor javasoljuk használni, ha az ár nem változik, hanem az érvényességi időt tolják ki.

2. Árak lezárása és új felvitele. Ezt akkor érdemes használni, ha valóban változott az ár. így visszamenőlegesen is megvan a hivatalos ár. 

![alt text](image-6.png)


