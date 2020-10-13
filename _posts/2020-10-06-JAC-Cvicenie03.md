---
layout: post
title:  "3. Cvičenie - Programovanie v jazyku C"
categories: [ Vyuka, JAC ]
image: /assets/images/JAC.jpg
author: ppatrik
---

Na hodine sme sa venovali hlavičkovým súborom a princípe ich kompilácie a buildovania/linkovania. 

### Zdrojové kódy z cvičenia

**prvy.c**
```
#include <stdio.h>
#include "kalkulacka.h"

int main() {
    int fahr, celsius;
    int lower, upper, step;
    
    lower = 0;
    upper = 300;
    step = 20;
    
    fahr = lower;
    while(fahr <= upper) {
      celsius = konvertuj(fahr);
      printf("%d\t%d\n", fahr, celsius);
      fahr = fahr + step;
    }
    
    return 0;
}
```

**kalkulacka.c**
```
int konvertuj(int fahr1) {
	return 5 * (fahr1 - 32) / 9;
}
```

**kalkulacka.h**
```
int konvertuj(int fahr);
```

**Makefile**
```
# linkovanie
prvy.exe: prvy.o kalkulacka.o
	gcc -Wall -o "prvy.exe" "kalkulacka.o" "prvy.o"

# kompilat zdrojoveho suboru prvy.c
prvy.o: prvy.c
	gcc -Wall -o "prvy.o" -c prvy.c

# kompilat zdrojoveho suboru kalkulacka.c
kalkulacka.o: kalkulacka.c
	gcc -Wall -o "kalkulacka.o" -c kalkulacka.c

test: prvy.exe
	./prvy.exe
	
full_test: $
	make clean && make test

clean: $
	rm prvy.exe prvy.o kalkulacka.o

```
