---
layout: post
title:  "11. Cvičenie - Programovanie v jazyku C"
categories: [ Vyuka, JAC, ZS2019 ]
image: /assets/images/JAC.jpg
author: ppatrik
---

**program.c**
```
#include <stdio.h>


void writeToFile() {
	FILE *file_resource;
	
	file_resource = fopen("nazov.txt", "w");
	fprintf(file_resource, "Hello");
	fclose(file_resource);
	
}


void readFromFile() {
	FILE *file_resource;
	
	file_resource = fopen("nazov.txt", "r");
	char buffer[1000];
	fscanf(file_resource, "%s", buffer);
	fclose(file_resource);
	
	printf("Zo suboru %s", buffer);
}


void appendToFile() {
	FILE *file_resource;
	
	file_resource = fopen("nazov.txt", "a");
	fprintf(file_resource, "Hello");
	fclose(file_resource);
}


void testForIOErrors() {
	FILE *file_resource;
	
	file_resource = fopen("nazov.txt", "r");
	fprintf(file_resource, "Hello");
	if(ferror(file_resource)) {
		printf("Nastala chyba pri zapisovani do suboru %d", ferror(file_resource));
	}
	fclose(file_resource);
}

int main(int argc, char *argv[]) {
	if (argc > 2) {
		
		FILE *file_from;
		FILE *file_to;
		file_from = fopen(argv[1], "r");
		if(ferror(file_from)) {
			printf("Nepodarilo sa otvorit zdrojovy subor");
			return ferror(file_from);
		}
		file_to = fopen(argv[2], "w");
		if(ferror(file_to)) {
			printf("Nepodarilo sa otvorit cielovy subor");
			return ferror(file_to);
		}
		
		char c;
		while((c = getc(file_from))!=EOF) {
			putc(c, file_to);
		}
		if(ferror(file_from)) {
			printf("Nepodarilo sa citat zdrojovy subor");
			return ferror(file_from);
		}
		if(ferror(file_to)) {
			printf("Nepodarilo sa zapisat cielovy subor");
			return ferror(file_to);
		}
		
		fclose(file_from);
		fclose(file_to);
		
		return 0;

	}
	
	return 1;
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
