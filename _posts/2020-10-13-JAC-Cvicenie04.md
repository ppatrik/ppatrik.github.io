---
layout: post
title:  "4. Cvičenie - Programovanie v jazyku C"
categories: [ Vyuka, JAC, ZS2019 ]
image: /assets/images/JAC.jpg
author: ppatrik
---

### Zdrojové kódy z cvičenia

**prvy.c**
```
#include "databaza.h"

int main() {
	connect();
}
```

**databaza.h**
```
#ifndef _DATABAZA_H_

#define _DATABAZA_H_ 1

#include <stdio.h>
#include "bl.h"

int loadUserIdFromDb();

void connect();

#endif

```

**databaza.c**
```
#include "databaza.h"

void connect() {
	printf("connect::\n");
	int id;
	printf("connect::Pripojili sme sa\n");
	id = getUserId();
	printf("connect::%d\n", id);
}

int loadUserIdFromDb() {
	printf("loadUserIdFromDb\n");
	return 125;
}
```

**bl.h**
```
#ifndef _BL_H_

#define _BL_H_ 1

#include <stdio.h>
#include "databaza.h"

int getUserId();

#endif
```

**bl.c**
```
#include "bl.h"

int getUserId() {
	printf("getUserId\n");
	int string_id, id;
	string_id = loadUserIdFromDb();
	id = string_id;
	return id;
}
```

**Makefile**
```
# linkovanie
prvy.exe: prvy.o databaza.o bl.o
	gcc -Wall -o "prvy.exe" "databaza.o" "prvy.o" "bl.o"

# kompilat zdrojoveho suboru prvy.c
prvy.o: prvy.c
	gcc -Wall -o "prvy.o" -c prvy.c

# kompilat zdrojoveho suboru databaza.c
databaza.o: databaza.c
	gcc -Wall -o "databaza.o" -c databaza.c
	
# kompilat zdrojoveho suboru bl.c
bl.o: bl.c
	gcc -Wall -o "bl.o" -c bl.c

test: prvy.exe
	./prvy.exe
	
full_test: $
	make clean && make test

clean: $
	rm prvy.exe prvy.o databaza.o bl.o
```
