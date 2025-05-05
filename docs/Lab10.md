---
title: Laboratory Exercise 10
subtitle: System Modeling (VIMIAD03)
header: System Modeling (VIMIAD03)
---

Ez a labor a teljesítménymodellezés alkalmazásait fogja bemutatni. A laborfeladatok ezúttal magyarul lesznek, megoldásukhoz csak papírra és tollra, esetleg számológépre lesz szükség.



# Feladatok

## Diszk teljesítménye

Egy diszk 50 kérést szolgál ki másodpercenként. Minden kérés kiszolgálása 0,005 másodpercet vesz igénybe. A rendszerben nincs átlapolódás.

1. Mekkora a maximálisan kiszolgálható terhelés (érkezési ráta)?
2. Mekkora a kihasználtság?

## Zárthelyi megtekintése

 A zárthelyik megtekintése során a hallgatóknak lehetőségük van reklamálni esetleges javítási hibák miatt. Sikeres reklamáció esetén a pontszámuk módosításra kerül. Az első nagyfeladatból (F1) óránként 10 darabot képes átnézni egy javító, a második nagyfeladatból (F2) pedig 20 darabot. Mindkét feladathoz tartozik 1-1 javító, akik az adott feladatot javították. A továbbiakban készítsünk minden kérdéshez egy-egy folyamatmodellt és határozzuk meg, hogy óránként hány hallgató dolgozatát sikerül átnézni az egyes esetekben!

1. A hallgatók először az F1, majd az F2 feladatot nézetik át a javítóval.
2. A leleményes hallgatók a két feladatot külön-külön már egyszerre két javítónak adják oda, mivel külön lapra voltak írva. Mit nyerünk a párhuzamosítással?
3. A nagy tömeg miatt a hallgatók csak az egyik feladatukat nézetik át, mégpedig azt, amelyiknek a javítója éppen szabad.
4. Híre ment, hogy a második feladat javítója sokkal kevésbé szigorú, így a hallgatók 80%-a inkább kivárja ennél a javítónál a sort. A maradék 20% a másik javítónál reklamál az első feladattal kapcsolatban.
5. A hallgatók 10%-ának a reklamáció után már csak 1-2 pont kellene a jobb jegyhez, ezért újra és újra megpróbálkoznak a reklamációval. Feltételezhetjük, hogy a hallgatók az a) részben leírt reklamációs stratégiát használják.
6. Mi történne másként, ha bármelyik javító bármelyik feladatot hajlandó átnézni (de az egyes feladatok átnézése változatlan ideig tart), és így szeretnék a hallgatók az eredeti tervnek megfelelően először az F1, majd az F2 feladatot átnézetni a javítóval?

## Kétrétegű architektúra

Adott egy webszerver (WS) és két fürtözött adatbázisszerver (DB1, DB2). A két adatbázis szerver közt súlyozott round robin terheléselosztás alapján választunk, 1:2 arányban. Minden felhasználói kérés kiszolgálása során mindkét fajta erőforrást használjuk. A csúcsidőszakban 30 percig monitorozzuk a rendszert, ezalatt 9000 kérést szolgál ki. A szerveken mért foglaltsági idők: WS– 1350 s CPU idő; DB1– 810 s, DB2– 1320 s diszk IO idő.

1. Készítsünk folyamatmodellt a kérések feldolgozásáról a szöveg alapján!
2. Mekkora az egyes szerverek jelenlegi átbocsátása?
3. Mennyi időt töltenek egy-egy hozzájuk beérkezett kérés kiszolgálásával a szerverek?
4. Mekkora a rendszer maximális áteresztőképessége?
5. Miért nem egy féle foglaltsági időt vettünk figyelembe a két erőforrástípusnál?
6. Hol csal még így is a modell?

## Mikroszolgáltatás

Mikroszolgáltatásunk egy közelítő algoritmust implementál, melyet más szolgáltatások hálózaton keresztül építőkockaként felhasználhatnak a saját funkciójuk megvalósításához. Mivel sok egyforma kérés érkezik, a szolgáltatás gyorsítótárazza a válaszokat, így a korábban kiszámolt eredmények gyorsan visszaküldhetők. Maga a számítás egy igen költséges iteratív folyamat, amelyet addig kell ismételni, amíg a megoldás kellően precíz nem lesz.

Az alábbi modell a kísérleti futtatás tapasztalatait összegzi. Megfigyeléseink szerint a kérések 80%-a gyorsítótárból kiszolgálható, míg egy iteratív számítási lépés végén átlagosan 10% eséllyel lesz elég precíz a megoldás. A kétféle tevékenységhez megmértük az egyes erőforrások átlagos foglaltsági idejét is, ezt az alábbi ábrán a lépések felett tüntettük fel (csak a nem elhanyagolható ideig használt erőforrásokra).

A méréshez az élesben is használt szervert használtuk, amely 2 CPU-val, 1 RAM modullal és 1 diszkkel rendelkezik.

![Microservice](figs/microservice.png)

1. Ha mindegyik lépés esetén csak a leghosszabban használt erőforrást vesszük figyelembe, mekkora lehet a rendszer átbocsátóképessége?
2. Ha csak a mindkét lépés által jelentősebben használt, egyetlen közös diszk erőforrást tekintjük, akkor mekkora lehet a rendszer átbocsátóképessége?
3. Mekkora ez alapján a rendszer tényleges átbocsátóképessége? Melyik erőforrás (fel)skálázásával lehetne még tovább növelni?
4. Ha a kihasználtság 50%-os, és egy kérés beérkezésétől az eredmény visszaküldéséig (várakozással együtt) átlagosan 100~ms telik el, akkor átlagosan hány olyan kérés van a rendszerben, amelynek a feldolgozása még nem fejeződött be?

##  Sziget közlekedési hálózata

Egy sziget lakói minden reggel munkába menet átkelnek a szigetet ölelő tavon. Észak felé híd vezet, dél felé autóskomp. Az irányonként egysávos híd 200 m hosszú, és 60 km/h sebességgel szabad rajta haladni, a követési távolság (hátsó lámpától hátsó lámpáig 30 m) betartása mellett. A négy komphajó egyenként 15 percenként teszi meg a sziget-szárazföld-sziget kört, és így óránként négyen együtt legfeljebb 800 autót tudnak átvinni a szárazföldre.

1. Mekkora a híd átbocsátóképessége (észak felé)?
2. Hány autó fér el egy kompban?
3. A reggeli csúcsforgalomban mekkora a szigetet elhagyó két útvonal együttes átbocsátóképessége?
4. Ha délben a szárazföldi főutat baleset miatt lezárták, és a szigeten keresztül (a hídon, majd a kompon átkelve) terelik a forgalmat, mekkora a terelőútvonal átbocsátóképessége?
5. Valamelyik reggel 7:00 és 8:30 között 900 autó hagyta el a szigetet komppal. Mennyi volt ebben az időszakban a kompok átbocsátása és kihasználtsága?
6. A fenti mérésben átlagosan hány autó állt sorba egyszerre a parton, ha az autók jól időzítve, átlagosan fél perccel a beszállásuk előtt érkeztek kompkikötőhöz?
