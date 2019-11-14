---
layout: post
title:  "1. Projekt - Programovanie v jazyku C"
categories: [ Vyuka, JAC ]
image: /assets/images/JAC.jpg
author: ppatrik
---

>> Update 14.11.2019: \
>> **Zmena:** Boli upravené hlavičky metód. \
>> **Dôvod:** Pôvodné hlavičky neboli napísané správne.

Implementujte v jazyku ANSI C algoritmus [BubbleSort](https://en.wikipedia.org/wiki/Bubble_sort). Váš zdrojový kód musí obsahovať funkcie podľa nasl. hlavičkového súboru.

> Zoradzujete čísla (int) od najmenšieho po najväčšie.

## Hlavičkový súbor `progam.h`

```
# Algoritmus pre overenie či sa vám podarilo správne zoradiť pole
bool test_sort(int n, int input[])

# Algoritmus bubble sort
void swap(int *a, int *b);
int* bubbleSort(int n, int array[])
```

## Spôsob odovzdania:

Vytvorte repozitár na https://gitlab.science.upjs.sk s menom jac-2019-projekt-1. Repozitár musí obsahovať súbor `program.c` s vašou implementáciou. Tento repozitár mi nazdielate (Settings -> Members) na účet @patrik.pekarcik s minimálnou rolou Reporter. Po vytvorení a nazdielaní repozitára mi zašlite e-mailom informáciu o dokončeni zadania. \
Vypracovať do 22.11.2019 02:00.
> Ak ešte nemáte účet na gitlab.science.upjs.sk tak odporúčané používateľské meno je `meno.priezvisko`.
