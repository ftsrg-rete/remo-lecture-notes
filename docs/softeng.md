# Szoftvertechnológia extrafeladat 

Ez a feladat egyszeri alkalom, az alábbi leírás és pontozás csak a 2025 december 10-i laborra vonatkozik.

## 1. Bemutatkozás
- Röviden ki vagyok, mit fogunk ma csinálni.

## 2. Névsor, jelenlét és számolás
- Gyors névsorolvasás, jelenlét rögzítése.

## 3. Szabályok és pontozás
- **Alapfeladatok** teljesítése esetén: **+5 extra pont**
  - Nincs részpontozás.
- **IMSc feladat** teljesítése esetén: **+5 IMSc pont**
- **Questionnaire** (ma kiküldve):
  - **Vasárnapig** kitöltendő!

---

## 4. Promó – ReMo
- Kötelezően választható tárgy
- További infó: https://vik.bme.hu/page/1349/

## 5. Promó 2 – Külső előadás
- **Holnap:** vendégelőadó: **Daniel Siegl**
  - A SmartGit és a LemonTree vállalatok C-szintű technológiai vezetője

---

## 6. A mai labor menete

### 6.1 SmartGit és LemonTree megismerése
- Nézetek áttekintése:
  - **Local Files**: all files legördülő; jobb klikk mappán → *Open in Explorer*
  - **History nézet**: *Only current branch* / *All branches*

### Feladatok
1. Nyissuk meg EA-ben a **model.qeax** fájlt, nézzük át, majd zárjuk be.
2. Adjunk hozzá egy **README.txt** fájlt a *master* branchen.
3. Rebase-eljük erre a **feature** branchet.
4. Módosítsuk a README-t a *feature* branchen.
5. Diff megtekintése a két branch között *(CTRL + click)*
   - először: README.txt
   - majd: model.qeax
6. Checkout: master → új feature branch létrehozása.
7. „Integráljuk” a régi feature branchet a master-be.
8. Checkout: az új feature branchet → ezzel szimuláljuk egy másik ember köztes merge-jét.

---

### 6.2 Enterprise Architect
- Class diagram készítése a kiadott diagram alapján.
- A meglévő modell **módosítása**, kb. **15–20 modell elem**.
- Téma legyen olyasmi, ami érdekel – légy kreatív!

---

## 7. Merge a master-be
- Saját feature branch → merge → **konfliktusok feloldása!**
- **Extra 5 pont**, ha sikerül a merge.

---

## 8. IMSc feladat (párban)
1. GitHub repó létrehozása.
2. Feltöltés két külön branchre.
3. Mindkét branch-be merge-elni a másikat.

### IMSc értékelési feltételek
**+5 IMSc pont**, ha teljesül:
- mindkét képernyőn **ugyanaz a modell**,
- a módosítások felpusholva mindkét branch-re,
- LemonTree nem lát diffet a két branch között,
- a végső modell **mindkét módosítás elemeit** tartalmazza.
