---
layout: post
title:  "Programovanie v jazyku C - 1. Cvičenie"
categories: [ Vyuka, JAC ]
image: assets/images/1.jpg
author: ppatrik
---

## 3. Cvičenie

Na hodine sme sa venovali hlavičkovým súborom a princípe ich kompilácie a buildovania/linkovania. 

### Zdrojové kódy z cvičenia

**prvy.c**
```
#include <stdio.h>
#include "konverzie.h"


int main() {
	int startF;
	startF = 0;
	int f;
	float c;

	for (f = startF; f <= MAX_F; f += 10) {
		c = konvertujNaCelzius(f);
		printf("%3d %6.2f\n", f, c);
	}
	
    return 0;
}
```

**konverzie.c**
```
float konvertujNaCelzius(int fahrenheit) {
	return (fahrenheit-32) * 5./9;
}
```

**konverzie.h**
```
float konvertujNaCelzius(int fahrenheit);
```

**Makefile**
```
# Prelinkovanie a vytvorenie spustitelneho suboru
prvy.exe: prvy.o konverzie.o
	gcc -Wall -o "prvy" "konverzie.o" "prvy.o"

# Vytvorenie kompilatu z prvy.c
prvy.o: prvy.c
	gcc -Wall -o "prvy.o" -c "prvy.c"

# Vytvorenie kompilatu z konverzie.c	
konverzie.o: konverzie.c
	gcc -Wall -o "konverzie.o" -c "konverzie.c"

# Spustenie programu
test: prvy.exe
	./prvy.exe

# Popratanie na disku
clean: $
	rm prvy.o prvy.exe konverzie.o
```

