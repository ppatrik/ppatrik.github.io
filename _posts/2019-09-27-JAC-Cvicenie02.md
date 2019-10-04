---
layout: post
title:  "Programovanie v jazyku C - 2. Cvičenie"
categories: [ Vyuka, JAC ]
image: assets/images/1.jpg
author: ppatrik
---

## 2. Cvičenie

### Rozcvička - Prevodník medzi Fahrenheit a Celsium

```
#include <stdio.h>

int main() {
    int fahr, celsius;
    int lower, upper, step;
    
    lower = 0;
    upper = 300;
    step = 20;
    
    fahr = lower;
    while(fahr <= upper) {
      celsius = 5 * (fahr - 32) / 9;
      printf("%d\t%d\n", fahr, celsius);
      fahr = fahr + step;
    }
    
    return 0;
}
```

### Dátové typy

* int
* char
* float - single-precision
* double - double-precision

#### Modifikátory

Modifikovanie veľkosti dátového typu

* long _
  * long int
  * long long int
* short _
  * short int
  
Modifikovanie prístupu k premenným

* const - premenná môže byť inicializovaná len raz
* extern - definuje lokalnu referenciu (vo funkcii) na globálnu premennú

### Riadenie toku

Syntax cyklov
```
while(...) {
  ...
}
#
do {
  ...
} while(....);
#
for(..; ..; ..) {
  ...
}
```

Syntax podmienok
```
if() {
  ...
} else if() {
  ...
} else {
  ...
}
```

### Makrá (#define)

> V jazyku C vieme definovať konštanty formou makier. Tieto su v zdrojovom kóde prepísané ešte pred kompiláciou.

```
#define NAZOV_MAKRA 125

int main() {
  printf(NAZOV_MAKRA);
  return 0;
}
```

### Funkcie

```
/* hlavička funkcie musí byť na začiatku */
int konverzia(int vstup);

main() {
  ....
  konverzia(); /* ak by sme nemali hlavičku alebo implementáciu funkcie konverzia nad funkciou main tak kompilátor vyhlási chybu */
}

int konverzia(int vstup) {
  ....
  return vystup;
}
```

