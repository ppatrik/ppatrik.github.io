---
layout: post
title:  "6. Cvičenie - Programovanie v jazyku C"
categories: [ Vyuka, JAC ]
image: /assets/images/JAC.jpg
author: ppatrik
---

### ANSI C Prevodna tabulka

[ASCII Tabulka](https://i.alza.sk/Foto/ImgGalery/Image/Article/ascii-tabulka-lightbox.jpg)

### Zdrojové kódy z cvičenia

**main.c**
```
#include <stdio.h>

int main() {
	int cisla[5];
	cisla[0] = 1;
	cisla[1] = 2;
	cisla[2] = 3;
	cisla[3] = 4;
	cisla[4] = 5;
	int *cislaSmernik;
	cislaSmernik = cisla;
	printf("%d,%d,%d,%d,%d\n", cisla[0], cisla[1], cisla[2], cisla[3], cisla[4]);
	printf("%d\n", sizeof(int)); // 4
	printf("%d\n", cisla); // 6422280
	printf("%d\n", *(cisla + 1)); // 6422284
	printf("%d\n", *(cisla + 2));
	
	cislaSmernik++;
	printf("%d,%d,%d,%d,%d\n", cislaSmernik[0], cislaSmernik[1], cislaSmernik[2], cislaSmernik[3], cislaSmernik[4]);
	
	char text[100] = "JAC";
	
	printf("%s\n", text);
	text[3] = '5';
	printf("%s\n", text);
	
	struct Bod {
		int x;
		int y;
	};
	typedef struct Bod Point;
	struct Obdlznik {
		char id;
		float objem;
		Point zaciatok;
		Point koniec;
	};
	
	union viactvarnost {
		char znak;
		float decimal;
		int cislo;
	};
	
	
	printf("%d\n", sizeof(struct Bod));
	printf("%d\n", sizeof(Point));
	
	Point lavyBod;
	lavyBod.x = 10;
	lavyBod.y = 20;
	printf("%d - %d\n", lavyBod.x, lavyBod.y);
	
	struct Student {
		int odbor;
		int rocnik;
	}
	
	struct Ucitel {
		int odbor;
		int vek;
		int dosiahnute_vzdelanie;
	}
	
	union StudentUcitel {
		struct Student student;
		struct Ucitel ucitel;
	}
	
	struct User {
		char username[100];
		char type;
		union StudentUcitel;
	}
	
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
