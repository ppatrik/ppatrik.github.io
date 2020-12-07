---
layout: post
title:  "10. Cvičenie - Programovanie v jazyku C"
categories: [ Vyuka, JAC ]
image: /assets/images/JAC.jpg
author: ppatrik
---

**program.c**
```
#include <stdio.h>

void zapisDoSuboru() {
	FILE *file_resource;
	
	file_resource = fopen("test.txt", "w");
	fprintf(file_resource, "Test");
	fclose(file_resource);
}

void doplnDoSuboru() {
	FILE *file_resource;
	
	file_resource = fopen("test.txt", "a");
	fprintf(file_resource, "Doplnujem");
	fclose(file_resource);
}

void citajZoSuboru() {
	char buffer[40];
	
	FILE *file_resource;
	file_resource = fopen("test.txt", "r");
	fscanf(file_resource, "%s", buffer);
	fclose(file_resource);
	printf("%s", buffer);
}

struct Student {
	char meno[10];
	int vek;
	int pocetPredmetov;
};

int main() {
	FILE *file_resource;
	
	file_resource = fopen("databaza.txt", "r");

	int pocetZaznamov;
	fscanf(file_resource, "%d", &pocetZaznamov);
	printf("Pocet zaznamov v DB je %d\n", pocetZaznamov);
	
	int i;
	for (i = 0; i < pocetZaznamov; i++) {
		struct Student riadok;
		fscanf(file_resource, "%s %d %d", &riadok.meno, &riadok.vek, &riadok.pocetPredmetov);
		
		printf("%d. riadok - Meno: %s, Vek: %d, Pocet predmetov: %d\n", i+1, riadok.meno, riadok.vek, riadok.pocetPredmetov);
	}

	fclose(file_resource);
	return 0;
}
```

**Makefile**
```
main.exe: main.o 
	gcc -o "main" "main.o"

main.o: main.c
	gcc -o "main.o" -c "main.c"

clean:
	rm main.o main.exe
```
