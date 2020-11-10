---
layout: post
title:  "7. Cvičenie - Programovanie v jazyku C"
categories: [ Vyuka, JAC ]
image: /assets/images/JAC.jpg
author: ppatrik
---

### Zdrojové kódy z cvičenia

**main.c**
```
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

/*int strlen(char *text) {
	int i = 0;
	
	while(text[i] != '\0') {
		i++;
	}
	
	return i;
}*/


/* metodu na spojenie dvoch stringov */

char *concat(char *A, char *B) {
	int velkostA = strlen(A);
	int velkostB = strlen(B);
	
	char *novyString = (char *) malloc((velkostA + velkostB + 1) * sizeof(char));
	/*char *novyString = (char *) calloc(velkostA + velkostB + 1, sizeof(char));*/
	
	int i;
	i = 0;
	while(A[i] != '\0') {
		novyString[i] = A[i];
		i++;
	}
	
	int j;
	j = 0;
	while(B[j] != '\0') {
		novyString[i] = B[j];
		i++;
		j++;
	}
	novyString[i] = '\0';
	
	
	return novyString;
	
}

int main() {
	
	char *A = "AhojA";
	char *B = "Svet";
	
	printf("%s %s\n", A, B);
	
	printf("%d %d\n", sizeof(A), sizeof(B));
	
	char *N = concat(A, B);
	
	printf("%s\n", N);
	
	printf("%d\n", &N);
	
	free(N);
	
	printf("%s\n", N);
	printf("%d\n", &N);
	
	return 0;
}


struct Uzol {
	int value;
	struct Uzol *next;
};

void test() {
	struct Uzol *head = {value=1, next = NULL};
	struct Uzol *p, *q;
	
	/* Prvy - nespravny */
	for (p = head; p != NULL; p = p->next) {
		free(p);
	}
	
	/* Druhy - spravny */
	for (p = head; p != NULL; p = q) {
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
