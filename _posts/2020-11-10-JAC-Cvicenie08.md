---
layout: post
title:  "8. Cvičenie - Programovanie v jazyku C"
categories: [ Vyuka, JAC ]
image: /assets/images/JAC.jpg
author: ppatrik
---

### Zdrojové kódy z cvičenia

**main.c**
```
#include <stdio.h>
#include <stdlib.h>
#include <ctype.h>
#include <string.h>

void funkciaSArgumentami(int argc, char *argv[]) {
	printf("funkciaSArgumentami\n");
	printf("argc = %d\n", argc);
	
	int i;
	for (i = 0; i < argc; i++) {
		printf("argv[%d] = %s\n", i, argv[i]);
	}
}

int main(int argc, char *argv[]) {
	
	printf("argc = %d\n", argc);
	
	int i;
	for (i = 0; i < argc; i++) {
		printf("argv[%d] = %s\n", i, argv[i]);
	}
	
	if(argc > 1) {
		
		if(strcmp(argv[1], "atoi") == 0) {
			if(argc > 2) {				
				int vstupneCislo = atoi(argv[2]);
				printf("Praca s cislom %d\n", vstupneCislo);
			} else {
				printf("Musis zadat aj duhy ciselny argument");
				return 2;
			}
		}
		
		if(strcmp(argv[1], "fsa") == 0) {
			char *argv2[2];
			argv2[0] = "funkciaSArgumentami";
			argv2[1] = "Dominik";
			
			funkciaSArgumentami(2, argv2);
		}

		if(strcmp(argv[1], "gc") == 0) {
			int a = getchar();
			putchar(toupper(a));
		}
		
		if(strcmp(argv[1], "scanf") == 0) {
			char meno[20];
			printf("Zadaj svoje meno: ");
			scanf("%s", meno);
			printf("Ahoj %s!\n", meno);
			
			printf("Zadaj svoje meno: ");
			scanf("%s", meno);
			printf("Ahoj %s!\n", meno);
			
			printf("Zadaj svoje meno: ");
			scanf("%s", meno);
			printf("Ahoj %s!\n", meno);
		
		}
		
		return 0;
	}
	
	
	printf("Musis zadat aspon jeden argument atoi, fsa, gc alebo scanf.");
	return 1;
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

## Spôsoby spúšťania jednotlivých metód

- `main.exe < input.txt` - Namiesto manuálneho vkladania štanardného vstupu vkladáme vstup zo súbora.
- `main.exe > output.txt` - Výstup z programu je uložený do súboru.
- `main.exe | grep test` - Výstup z programu je cez pipe spravovaný ďalším programom napr. `grep test`.
- `main.exe 1` - Spustenie c programu s jedným argumentom.
