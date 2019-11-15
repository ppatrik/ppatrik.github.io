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
#include <ctype.h>
#include <string.h>

void test1() {
	char meno[20];
	printf("Zadaj svoje meno: ");
	scanf("%s", meno);
	int den, rok, mesiac;	
	printf("Ahoj %s\n", meno);
	/*scanf("%d.%d.%d", &den, &mesiac, &rok);*/
}

void test2 () {
	int c = getchar();
	int b = getchar();
	int a = getchar();
	if(c != EOF) {
		putchar(toupper(c));
	}
	if(b != EOF) {	
		putchar(toupper(b));
	}
	if(a != EOF) {	
		putchar(toupper(a));
	}
}

void test3() {
	/* toto nebude zverejnené */
}

void test4(int argc, char *argv[]) {
	printf("Pocet argumentov: %d\n", argc);
	int i;
	for(i = 0; i <  argc;i++) {
		printf("%d: %s\n", i+1, argv[i]);
	}
}

int main(int argc, char *argv[]) {
	if(argc < 2) {
		printf("Prosim zadaj argument 1 alebo 2 alebo 3 alebo 4.\n");
		return 1;
	}
	char *program = argv[1];
	if(strcmp(program, "1") == 0) {
		test1();
		return 0;
	}
	if(strcmp(program, "2") == 0) {
		test2();
		return 0;
	}
	if(strcmp(program, "3") == 0) {
		test3();
		return 0;
	}
	if(strcmp(program, "4") == 0) {
		test4(argc, argv);
		return 0;
	}
	printf("Zadal si nespravny argument.\n");
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

## Spôsoby spúšťania jednotlivých metňod

- `main.exe < input.txt` - Namiesto manuálneho vkladania štanardného vstupu vkladáme vstup zo súbora.
- `main.exe > output.txt` - Výstup z programu je uložený do súboru.
- `main.exe | grep test` - Výstup z programu je cez pipe spravovaný ďalším programom napr. `grep test`.
- `main.exe 1` - Spustenie c programu s jedným argumentom.
