---
title: Laboratory Exercise 2
subtitle: System Modeling (VIMIAD03)
header: System Modeling (VIMIAD03)
---

# Eszközhasználati feladatok

A csomagok, követelmények és használati esetek Enterprise Architectben való modellezésének megismeréséhez végezze el az alábbi útmutatókban írtakat:

1. [Projects and Packages](https://ftsrg-rete.github.io/remo-lecture-notes/first-project/)
2. [Requirements and Use cases](https://ftsrg-rete.github.io/remo-lecture-notes/usecase-and-requirement-guide/)

# Modellezési és módszertani feladatok

## 1. Rendszerkontextus meghatározása

Határozza meg magas szinten (az interakciók részletes kifejtése nélkül) a rendszerkontextust az alábbi rendszerekhez:

1. A *Budapest Mobility Engineering Zrt.* egy új, többféle fejlett vezetéstámogató funkcióval (pl. adaptív sebességtartó automatika, sávelhagyás-figyelmeztető rendszer, automatikus parkolás) felszerelt *középkategóriás személygépkocsit* tervez, megcélozva az 5 csillagos Euro NCAP biztonsági minősítés elérését és a vezeték nélküli funkciófrissítések támogatását.
2. A *MITion Systems* Tier-1-es beszállító *adaptív sebességtartó automatika* (Adaptive Cruise Control, ACC) rendszert fejleszt, amely radarérzékelőkből, elektronikus vezérlőegységből, fék-/gázpedál interfészekből és beágyazott szoftverből áll. Az ACC-t a Budapest Mobility Engineering Zrt. által gyártott járművekbe építik majd be.
3. A MITion Systems egyik belső szoftverfejlesztő egysége, a *Critical Controls*, beágyazott valós idejű *vezérlőszoftvert* implementál az adaptív sebességtartó automatika ECU-jához, amelynek célja az ISO 26262 ASIL-B szabványnak való megfelelés és a jármű CAN-hálózatával való zökkenőmentes integráció.
4. A *CampusMotion Technologies* egy nagy ipari campus számára fejleszt igény szerinti *autonóm transzfer szolgáltatást*, amely önvezető elektromos minibuszokból, útmenti infrastruktúrából, felhőalapú flottamenedzsmentből, felhasználói hitelesítésből és mobil foglalási alkalmazásokból áll, azzal a céllal, hogy csökkentse a magánautók használatát és optimalizálja a belső közlekedés hatékonyságát.

## 2. Használati esetek meghatározása

Végezze el a lenti részfeladatokat az 1.3. és 1.4. pontokban említett rendszerekre.

1. Stakeholderek és a rendszerrel közvetlenül interaktáló aktorok meghatározása
2. Use case-ek felderítése magas szinten (még forgatókönyv nélkül)
3. Use case forgatókönyvek kidolgozása, közben opcionálisan új use case-ek felvétele, amennyiben speciális esetek (extend, leszármazás) vagy több use case-ben is megjelenő lépéssorozatok (include) indokolják

   | **Element**      | **Description**                                                    |
   | ---------------- | ------------------------------------------------------------------ |
   | ID/Name          | Name or unique identifier of the use case.                         |
   | Involved Actors  | Involved actors in the use case, primary and secondary actors.     |
   | Preconditions    | What is needed/expected to start the use case?                     |
   | Primary Flow     | The most frequent/typical scenario of the use case ("Happy path"). |
   | Alternate Flow   | Less frequent scenarios.                                           |
   | Exceptional Flow | Scenarios not in support of the primary flow, e.g.: error handling |
   | Postconditions   | What is promised after successfully executing the use case?        |
   
4. Use case-ek közötti kapcsolatok ábrázolása use case diagramon

## 3. Követelmények meghatározása

1. Azonosítson a FURPS3 minden kategóriájához legalább egy követelményt a 2. feladatban említett két rendszerhez.  
   A funkcionális kategóriában törekedjen a rendszer legfelsőbb szintű, elsődleges funkcióját leíró követelmény általános meghatározására.
2. Bontsa tovább legalább két hierarchiaszinten az 3.1. pontban felvett funkcionális követelményt, és ábrázolja a létrejött követelményhierarchiát SysML követelménydiagramon.
