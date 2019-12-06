---
layout: post
title:  "2. Projekt - Programovanie v jazyku C"
categories: [ Vyuka, JAC ]
image: /assets/images/JAC.jpg
author: ppatrik
---

> Zadanie je v stadiu pripravovania, zatial tu nie su kompletne udaje. O dokonceni budete informovani e-mailom z AISu.

## Hlavičkový súbor `progam.h`

```
#define TRUE 1
#define FALSE 0

```

## Ukážka spusteného GUI programu

```
Vitajte v malej databovej verzii evidencie studentov 1.9.7.3.
> h
Zoznam povolenych akcii:
- h - zobrazí tieto informácie
- p - výpis z databázy na konzolu
- c - výpis velkosti databazy
- a - vytvoriť a pridať študenta
- u - upraviť študenta
- d - zmazať študenta
- o - otvoriť databázu zo súboru
- s - uložiť databázu do súboru
- q - ukončiť program
> p
|  ID |                 Meno |           Priezvisko |  Skupina | Body |
| --- | -------------------- | -------------------- | -------- | ---- |
> a
Zadajte meno: Patrik
Zadajte priezvisko: Pekarcik
Zadajte skupinu: Id
Zadajte body: 48
Patrik
> p
|  ID |                 Meno |           Priezvisko |  Skupina | Body |
| --- | -------------------- | -------------------- | -------- | ---- |
|   1 |               Patrik |             Pekarcik |       Id |   48 |
> c
Velkost databazy je 1
> s
Ulozene
> o
Hotovo nacitanych 1 studentov
> u
Zadajte ID studenta: 1
Zadajte meno []: Patko
Zadajte priezvisko []: Pekarcik
Zadajte skupinu []: Id
Zadajte body [0]: 49
> p
|  ID |                 Meno |           Priezvisko |  Skupina | Body |
| --- | -------------------- | -------------------- | -------- | ---- |
|   1 |                Patko |             Pekarcik |       Id |   49 |
> d
Zadajte ID studenta: 1
> c
Velkost databazy je 0
> q
Dakujem za pouzivanie
```

## Spôsob odovzdania:

Vytvorte repozitár na https://gitlab.science.upjs.sk s menom jac-2019-projekt-2. Repozitár musí obsahovať súbor `program.c` a `main.c` s vašou implementáciou. Tento repozitár mi nazdielate (Settings -> Members) na účet @patrik.pekarcik s minimálnou rolou Reporter. Po vytvorení a nazdielaní repozitára mi zašlite e-mailom informáciu o dokončeni zadania. \
Vypracovať do 24.12.2019 22:00.
> Ak ešte nemáte účet na gitlab.science.upjs.sk tak odporúčané používateľské meno je `meno.priezvisko`.

## Spôsob hodnotenia

TBD

Za každý oneskorený deň odovzdania je zrážka -0,5 boda.
