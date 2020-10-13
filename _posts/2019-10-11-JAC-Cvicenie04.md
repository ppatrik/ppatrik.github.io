---
layout: post
title:  "4. Cvičenie - Programovanie v jazyku C"
categories: [ Vyuka, JAC, ZS2019 ]
image: /assets/images/JAC.jpg
author: ppatrik
---

### Zdrojové kódy z cvičenia

**main.c**
```
#include <stdio.h>

#include "metoda1.h"
#include "metoda2.h"

int main() {
	int x = 2;
	int y = 4;
	metoda2(x);
	metoda2(y);
	metoda1(x, y);
	metoda3(x, y);
	
	int rola[3];
	rola[0] = 123;
	rola[1] = 42;
	rola[2] = 14;
	printf("%p\n", &rola[0]);
	int *pa = &rola[0];
	pa++;
	pa++;
	printf("%p\n", pa);
	printf("%d\n", *pa);
	
	return 0;
}
```

**metoda1.h**
```
#ifndef _METODA1_H_

	#define _METODA1_H_ 1
	
	#include "metoda2.h"

	void metoda1(int x, int y);

#endif
```

**metoda1.c**
```
#include "metoda2.h"

void metoda1(int x, int y) {
	int z = x + y;
	metoda2(z);
}
```

**metoda2.h**
```
#ifndef _METODA2_H_

	#define _METODA2_H_ 1

	#include <stdio.h>
	#include "metoda1.h"
	
	void metoda2(int x);
	void metoda3(int x, int y);

#endif


```

**metoda2.c**
```
#include <stdio.h>
#include "metoda1.h"

void metoda2(int x) {
	printf("%d\n", x);
}

void metoda3(int x, int y) {
	metoda1(x, y);
}

```

**Makefile**
```

main.exe: main.o metoda1.o metoda2.o
	gcc -Wall -o "main" "metoda1.o" "metoda2.o" "main.o"

metoda1.o: metoda1.c
	gcc -Wall -o "metoda1.o" -c "metoda1.c"

metoda2.o: metoda2.c
	gcc -Wall -o "metoda2.o" -c "metoda2.c"

main.o: main.c
	gcc -Wall -o "main.o" -c "main.c"

# Spustenie programu
test: main.exe
	./main.exe

# Popratanie na disku
clean: $
	rm *.o main.exe
```

