---
title: Laboratory Exercise 5
subtitle: System Modeling (VIMIAD03)
header: System Modeling (VIMIAD03)
---

A laboron használt kiinduló modell: [struct-method-lab-initial.qeax](https://github.com/ftsrg-rete/remo-lecture-notes/raw/refs/heads/master/docs/assets/struct-method-lab-initial.qeax)

# Rendszerspecifikáció

Egy adaptív sebességtartó rendszert (adaptive cruise control, ACC) tervezünk. A kiadott modell a sebességmérésre és ez alapján a motor vezérlésére fókuszál.

A sebességet két különböző módon mérjük egyszerre: 1) egy 3DM-GX5-10 IMU (Inertial Measurement Unit) közvetlenül mozgásadatokat szolgáltat a belső szenzorai alapján, míg 2) a négy kerék mozgását függetlenül mérjük enkóderekkel, egyel-egyel minden kerékhez. Az enkóderek adatait egy mikrokontrollerbe vezetjük, amely a 4 enkóder méréséből állít elő egyetlen értéket a jármű sebességére. 

A mikrokontrollerből származó aggregált adatok a fő logikai egységbe mennek tovább. A két sebességmérést az ACC fő logikai egysége dolgozza fel, amely szintén egy mikrokontroller. A kimenet egy parancs, hogy gyorsítson, lassítson vagy tartsa a jármű a sebességet. Az egyszeres hibapont (SPoF) kiküszöbölése érdekében a fő logikai egység meg van kettőzve. 

Egy FPGA szavazót használunk védelemként, hogy a rendszer a végső parancsot kiadja-e, vagy pedig biztonságos vészhelyzeti leállást kezdeményezzen. Az FPGA szavazó is duplikálva van, de a kettőzés nem egy külön szavazóval van megvalósítva, hanem az FPGA szavazók megkapják a másik FPGA kimenetét és folyamatosan összevetik a saját kimenetükkel, hogy amint eltérést észlelnek, a biztonságos vészhelyzeti leállítást kezdeményezzék. 

Minden mikrokontroller áramellátását a fő tápegység biztosítja egy-egy dedikált 5V-os tápszabályzón keresztül (minden mikrokontrollernek van saját tápszabályzója).

# Ismerkedés az ACC modellel

Ismerkedjen meg a kiinduló modellel! A modell struktúrájának átlátásában segít az overview package diagram – ebben találhatóak linkek a különböző diagramokra és megjegyzések a szerepükről.

# A modell kiegészítése

Egy adaptív sebességtartónak nem szimplán a sebességtartás a feladata: az adaptivitás azt jelenti, hogy figyelnie kell, nincs-e túl közel a jármű az előtte haladóhoz, és amennyiben igen, akkor lassítania kell, akkor is, ha a jármű a célsebességnél lassabban halad. Ehhez szükség van a távolság mérésére is, ami még nem szerepel a modellben (bár pár azzal kapcsolatos jegyzet már bekerült, és a tartandó távolság beállítására is szerepel már modellelem). A távolságmérést a hibatűrés jegyében az alábbi módon tervezzük megvalósítani: egy radart és egy lézeres távolságmérő szenzort is használunk egyszerre, mindkettő folyamatosan méri a távolságot, a mérésüket pedig egy dedikált mikrokontroller dolgozza fel, és egyetlen fúzionált értéket továbbít a vezérlésért felelős komponensnek. Egészítse ki a modellt távolságméréssel! A modellben már szereplő funkciók és platform komponensek mintájára vegye fel a szükséges új elemeket a funkcionális és platform modellben is, majd végezze el az allokációt, és ennek megfelelően egészítse ki a rendszerarchitektúra modellt! Ne felejtse el a létező komponensek interakciós pontjait (portok és ezek interfészei) is megfelelően bővíteni!
