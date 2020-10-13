---
layout: post
title:  "5. Cvičenie - Programovanie v jazyku C"
categories: [ Vyuka, JAC, ZS2019 ]
image: /assets/images/JAC.jpg
author: ppatrik
---

### Zdrojové kódy z cvičenia

**main.c**
```
#include <stdio.h>

void swap (int *a, int *b) {
	int temp;

	printf("SWAP a: %d, b: %d\n", a, b);	
	temp = *a;
	*a = *b;
	*b = temp;
	printf("SWAP a: %d, b: %d\n", a, b);

}

int swapTest() {
	int x = 34;
	int y = 14;
	int *px = &x;
	int *py = &y;
	printf("x: %d, y: %d\n", *px, *py);
	swap(px, py);
	printf("x: %d, y: %d\n", *px, *py);
	swap(&x, &y);
	printf("x: %d, y: %d\n", *px, *py);
	return 0;
}

int main() {
	char output[100] = "Ahojte studenti";
	printf("%s\n", output);
	int i;
	for (i = 0; i < 200; i++) {
		printf("%3d: %3d %c\n", i, output[i], output[i]);
	}
	output[15] = '5';
	printf("%s\n", output);
	char *output2 = &output[5];
	printf("%s\n", output2);
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

