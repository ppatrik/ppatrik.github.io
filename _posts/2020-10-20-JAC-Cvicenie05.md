---
layout: post
title:  "5. Cvičenie - Programovanie v jazyku C"
categories: [ Vyuka, JAC, ZS2019 ]
image: /assets/images/JAC.jpg
author: ppatrik
---

### Správa pamäte v ANSI C aplikácii

https://www.youtube.com/watch?v=_8-ht2AKyH4 0:00 - 8:00

### Zdrojové kódy z cvičenia

**main.c**
```
#include <stdio.h>

int main() {
	printf("int %d\n", sizeof(int));
	printf("long int %d\n", sizeof(long int));
	printf("long long int %d\n", sizeof(long long int));
	printf("short int %d\n", sizeof(short int));
	printf("char %d\n", sizeof(char));
	printf("float %d\n", sizeof(float));
	printf("double %d\n", sizeof(double));
	
	printf("int* %d\n", sizeof(int*));
	printf("char* %d\n", sizeof(char*));
	
	
	int a;
	a = 125;
	printf("Umiestnenie premennej (referencia) a %d s hodnotou %d\n", &a, a);
	
	int *smernik;
	smernik = &a;
	printf("Hodnota premennej smernik %d\n", smernik);
	printf("Dereferencie smernika %d\n", *smernik);
	
	*smernik = 126;
	printf("a = %d, *smernik = %d\n", a, *smernik);

	
	return 0;
}
```

**Makefile**
```
main.exe: main.o 
	gcc -Wall -o "main" "main.o"

main.o: main.c
	gcc -Wall -o "main.o" -c "main.c"

clean:
	rm main.o main.exe
```
