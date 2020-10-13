---
layout: post
title:  "6. Cvičenie - Programovanie v jazyku C"
categories: [ Vyuka, JAC, ZS2019 ]
image: /assets/images/JAC.jpg
author: ppatrik
---

### Zdrojové kódy z cvičenia

**main.c**
```
#include <stdio.h>

struct Point {
	int x;
	int y;
};

struct Rect {
	struct Point zaciatok;
	struct Point koniec;
};

struct Vrchol {
	int x;
	struct Vrchol *lavy;
	struct Vrchol *pravy;
};

typedef struct Rect Rectangle;

typedef struct Rect *RectanglePointer;

int obsah (RectanglePointer obdlznik) {
	int a, b;
	a = obdlznik->koniec.x - obdlznik->zaciatok.x;
	b = (*obdlznik).koniec.y - (*obdlznik).zaciatok.y;
	return a*b;
}

int main() {
	
	Rectangle obdlznik;
	
	printf("Zaciatok - x: %3d y: %3d\n", obdlznik.zaciatok.x, obdlznik.zaciatok.y);
	printf("Koniec   - x: %3d y: %3d\n", obdlznik.koniec.x, obdlznik.koniec.y);
	
	obdlznik.zaciatok.x = 10;
	obdlznik.zaciatok.y = 10;
	obdlznik.koniec.x = 12;
	obdlznik.koniec.y = 12;
	
	
	printf("Zaciatok - x: %3d y: %3d\n", obdlznik.zaciatok.x, obdlznik.zaciatok.y);
	printf("Koniec   - x: %3d y: %3d\n", obdlznik.koniec.x, obdlznik.koniec.y);
	
	printf("Obsah je %d\n", obsah(&obdlznik));
	
	printf("int           %2d \n", sizeof(int));
	printf("char          %2d \n", sizeof(char));
	printf("long          %2d \n", sizeof(long));
	printf("short         %2d \n", sizeof(short));
	printf("float         %2d \n", sizeof(float));
	printf("double        %2d \n", sizeof(double));
	printf("struct Point  %2d \n", sizeof(struct Point));
	printf("struct Rect   %2d \n", sizeof(struct Rect));
	printf("Rectangle     %2d \n", sizeof(Rectangle));
	printf("RectanglePointer  %2d \n", sizeof(RectanglePointer));
	
	union u_daco {
		int integer;
		float float_value;
		char znak;
		char *string;
	} mix;
	
	mix.integer = 6548712;
	printf("obsah mixu: %c\n", mix.znak);
	printf("obsah mixu: %d\n", mix.integer);
	mix.znak = 'a';
	
	printf("obsah mixu: %c\n", mix.znak);
	printf("obsah mixu: %d\n", mix.integer);
	printf("velkost mix  %2d \n", sizeof(mix));
	
	
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
