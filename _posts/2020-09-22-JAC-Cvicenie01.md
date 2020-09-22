---
layout: post
title:  "1. Cvičenie - Programovanie v jazyku C"
categories: [ Vyuka, JAC ]
image: /assets/images/JAC.jpg
author: ppatrik
---

### Príprava vývojového prostredia (Windows)

Pre vývoj pod platformou Windows potrebujeme nainštalovať niekoľko nástrojov pomocou ktorých budeme môcť kompilovať a spúšťať programy v jazyku C.
Prvým programom je [MinGW](https://osdn.net/projects/mingw/downloads/68260/mingw-get-setup.exe/).
Po stiahnutí ho nainštalujeme do priečinka `C:\MinGW` (Pozor: cesta nesmie obsahovať medzery, preto sa neinštaluje do Program files).
V inštalačnom okne MinGW Installation Manager vyberte tieto balíčky **mingw32-base-bin**, **mingw32-gcc-ada-bin** a **msys-base-bin**.
Inštaláciu balíčkov spustíme cez Menu -> Installation -> Apply changes.

V rámci cvičení budeme používať vývojové prostredie [Geany](https://portableapps.com/apps/development/geany_portable).
Po stiahnutí spustíme exe súbor ktorý rozbalí prostredie do ľubovolného priečinka (napr. `C:\GeanyPortable`).

Aby sme mohli v rámci operačného systému windows používať nástroje doinštalované cez MinGW potrebujeme pridať priečinky do premennej prostredia `PATH` (Odporúčam len pre aktuálneho používateľa).
V prípade, že nemáme možnosť nastaviť premenné prostredia môžeme ich nastaviť v príkazovom riadku, z ktorého budeme spúštať Geany a kompilácie, nasledujúcim príkazom:

```
set PATH=C:\MinGW\bin;C:\MinGW\msys\1.0\bin;C:\MinGW\mingw32\bin;%PATH%
```

Následne môžeme otestovať úspešnosť inštalácie

```
$ set PATH=C:\MinGW\bin;C:\MinGW\msys\1.0\bin;C:\MinGW\mingw32\bin;%PATH%
$ make --version
$ gcc -v
```

### Zdrojový kód z cvičenia
