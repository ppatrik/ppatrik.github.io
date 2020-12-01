---
layout: post
title:  "10. Cvičenie - Programovanie v jazyku C"
categories: [ Vyuka, JAC ]
image: /assets/images/JAC.jpg
author: ppatrik
---

Na hodine sme sa venovali existujúcim operátorom v c a pokúsili sme sa ich spoločnými silami zoradiť podľa toho v akom poradí sú spracovávané.

| P.č. | Operátory       |
|------|-----------------|
|   1. | `()` `[]` `->` `.`      |
|   2. | `!` `~` `++` `--` `+` `-` `*` `&` `(type)` `sizeof` |
|   3. | `*` `/` `%` |
|   4. | `+` `-` |
|   5. | `<<` `>>` |
|   6. | `<` `<=` `>` `>=` |
|   7. | `==` `!=` |
|   8. | `&` |
|   9. | `^` |
|  10. | `\|` |
|  11. | `&&` |
|  12. | `\|\|` |
|  13. | `?:` |
|  14. | `=` `+=` `-=` `\*=` `/=` `%=` `&=` `^=` `\|=` `<<=` `>>=` |
|  15. | `,` |

## Popis operátorov

### Unárne

* `!` - negácia.
* `~` - bitová inverzia.
* `++` - pripočítanie jednotky. Príklady `++i`, `i++`.
* `--` - odpočítanie jednotky. Príklady `--i`, `i--`.
* `+`, ˙-˙ - prefixovo zadané znamienko. Príklady `-9`, `-i`.
* `*`, `&` - referencia a dereferencia adresy premennej (smerníky).
* `(type)` - pretypovanie premennej. Príklad `int code = 9; char znak = (char) code;`.
* `sizeof` - zistenie bitovej veľkosti premennej. Príklad `int velkost = sizeof int;`.

### Binárne

* `*`, `/`, `%` - násobenie, delenie a modulo (zvyšok po delení).
* `+`, `-` - sčítanie a odčítanie.
* `<<`, `>>` - bitový posun vľavo alebo vpravo.
* `<`, `<=`, `>`, `>=`, `==`, `!=` - porovnávacie operátory.
* `&`, `^`, `\|` - bitové operácie AND, XOR a OR.
* `&&`, `\|\|` - binárne operácie AND a OR.
* `=`, `+=`, `-=`, `\*=`, `/=`, `%=`, `&=`, `^=`, `\|=`, `<<=`, `>>=` - priraďovací operátor so skrátenými aritmetickými operáciami.


### Ternárne

* `?:` - Podmienkový if-else blok v jednom riadku. Príklad `x==y ? "ano" : "nie"`.
