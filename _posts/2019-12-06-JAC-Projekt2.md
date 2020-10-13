---
layout: post
title:  "2. Projekt - Programovanie v jazyku C"
categories: [ Vyuka, JAC, ZS2019 ]
image: /assets/images/JAC.jpg
author: ppatrik
---

> Update 18.12.2019: \ Zmena: Boli upravené hlavičky metód, zmena na smerníky. \ Dôvod: Pôvodné hlavičky by kopírovali objekty.

Naprogramujte CRUD konzolovú aplikáciu pre evidenciu študentov predmetu. Aplikácia nech pomocou štandardného vstupu komunikuje s používateľom a povolí mu operácie vloženia, upravenia a zmazania študentov. Taktiež nech obsahuje podporu ukladania študentov na disk do súboru a aj načítanie z disku. Program rozdeľte do dvoch častí: 
1. `program.c` - táto časť má obsahovať rozhranie popísané hlavičkovým súborom `program.h` uverejnením nižšie v zadaní.
2. `main.c` - táto časť má obsahovať konzolové prostredie pomocou, ktorého bude používateľ aktívne vykonávať operácie z `program.h`.

## Hlavičkový súbor `progam.h`

> Tento súbor neupravujte, len ho importujte.

```
#define TRUE 1
#define FALSE 0

#define FILE_DB "database.txt"

typedef struct StudentStruct {
    char meno[20];
    char priezvisko[20];
    char studijna_skupina[8];
    int pocet_bodov;
} Student;

/* Vypis informacii na konzolu. Iba tieto dve metody maju povolene vykonavat printf. */
void print_help();
void print_table();
/*
 * Bonus: Vytvorte metody sprint_help a sprint_table tak aby nevypisovali nič priamo na konzolu ale,
 * text vrátia ako návratovú hodnotu volania funkcie.
 * char* sprint_help();
 * char* sprint_table();
 */

/* Pomocna metoda pre ziskanie noveho prazdenho studenta, v ramke */
Student *init_student();

/* CRUD operacie s databazou */
int add_student(Student *student);
Student *get_student(int identifier);
int update_student(int identifier, Student *student); 
int delete_student(int identifier);

/* Doplnkove informacie o databaze */
int get_database_size();

/* Ulozenie databazy na diks */
int save_to_file(char *file_name);
int open_from_file(char *file_name);
```

## Ukážka spusteného konzolového GUI programu

```
Vitajte v malej databazovej verzii evidencie studentov 1.9.7.3.
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

1. časť `program.c` (max. 8 bodov)
  - Implementovanie všetkých metód podľa hlavičkového súboru: 1b
  - Implementácia efektívnej databázovej štruktúry: 2b
  - Implementácia CRUD operácií: 3b
  - Návrh štruktúry súboru: 1b
  - Ukladanie do súbora a čítanie zo súbora: 1b
2. časť `main.c` (max. 4 bodov)
  - Funkčné GUI: 2b
  - Všetky podporované operácie GUI popísané v helpe: 1b
  - GUI stále vypíše čo má používateľ vložiť (User Experience): 1b
Bonus:
  - Implementácia `sprint_*`: 1b

Za každý oneskorený deň odovzdania je zrážka -0,5 boda.
