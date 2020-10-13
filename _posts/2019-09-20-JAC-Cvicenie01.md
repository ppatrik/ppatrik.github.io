---
layout: post
title:  "1. Cvičenie - Programovanie v jazyku C"
categories: [ Vyuka, JAC, ZS2019 ]
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
GNU Make 3.81
Copyright (C) 2006  Free Software Foundation, Inc.
This is free software; see the source for copying conditions.
There is NO warranty; not even for MERCHANTABILITY or FITNESS FOR A
PARTICULAR PURPOSE.

This program built for i686-pc-msys

$ gcc -v
Using built-in specs.
COLLECT_GCC=gcc
COLLECT_LTO_WRAPPER=c:/mingw/bin/../libexec/gcc/mingw32/8.2.0/lto-wrapper.exe
Target: mingw32
Configured with: ../src/gcc-8.2.0/configure --build=x86_64-pc-linux-gnu --host=mingw32 --target=mingw32 --prefix=/mingw --disable-win32-registry --with-arch=i586 --with-tune=generic --enable-languages=c,c++,objc,obj-c++,fortran,ada --with-pkgversion='MinGW.org GCC-8.2.0-3' --with-gmp=/mingw --with-mpfr=/mingw --with-mpc=/mingw --enable-static --enable-shared --enable-threads --with-dwarf2 --disable-sjlj-exceptions --enable-version-specific-runtime-libs --with-libiconv-prefix=/mingw --with-libintl-prefix=/mingw --enable-libstdcxx-debug --with-isl=/mingw --enable-libgomp --disable-libvtv --enable-nls --disable-build-format-warnings
Thread model: win32
gcc version 8.2.0 (MinGW.org GCC-8.2.0-3)
```

### Zdrojový kód z cvičenia

#### prvy.c
```
#include <stdio.h>

int main() {
    printf("Hello World\n");
    return 0;
}
```

#### Makefile
```
prvy: prvy.c
    gcc -Wall -o prvy prvy.c

clean:
    rm prvy.exe
```
