---
layout: post
title:  "7. Cvičenie - Programovanie v jazyku C"
categories: [ Vyuka, JAC, ZS2019 ]
image: /assets/images/JAC.jpg
author: ppatrik
---

### Zdrojové kódy z cvičenia

**main.c**
```
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

char *concat(char *prvy, char *druhy) {
	int prvyDlzka = strlen(prvy);
	int druhyDlzka = strlen(druhy);
	int vyslednaDlzka = prvyDlzka + druhyDlzka;
	//char *vysledneSlovo = (char *) malloc((vyslednaDlzka + 1) * sizeof(char));
	char *vysledneSlovo = (char *) calloc(vyslednaDlzka + 1, sizeof(char));
	int i;
	for(i = 0; i < prvyDlzka; i++) {
		vysledneSlovo[i] = prvy[i];
	}
	for(i = 0; i < druhyDlzka; i++) {
		vysledneSlovo[prvyDlzka + i] = druhy[i];
	}
	vysledneSlovo[prvyDlzka + druhyDlzka] = '\0';
	return vysledneSlovo;
}

int main() {
	char *prvyString = "Ahojte";
	printf("%d\n", sizeof(char));
	char *spojenyString = concat(prvyString, "Studenti");
	printf("\"%s\"\n", spojenyString);
	free(spojenyString);
	return 0;
}

void test() {
	//1 - WRONG
	for (p = head; p != null; p = p->next) {
		free(p);
	}
	//2 - CORRECT
	for (p = head; p != null; p = q) {
		q = p->next;
		free(p);
	}
	
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
