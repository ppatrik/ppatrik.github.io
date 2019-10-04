---
layout: post
title:  "Diplomová práca"
categories: [ Projekty ]
image: /assets/images/3.jpg
author: ppatrik
---

## Komponentové a udalosťami riadené programovanie zariadení na platforme Arduino
Autor: **Patrik Pekarčík** \\
Vedúci práce: **František Galčík**

### Elevator pitch
Navrhli a implementovali sme nový prístup k programovaniu na zariadeniach Arduino. Náš prístup je postavený na myšlienke komponentov a udalostí, ktorý poznáme zo sveta programovania desktopových a mobilných aplikácií. K novému prístupu sme implementovali aj integrované vývojové prostredie (IDE) pre jednoduchšie presadenie. IDE je dostupné formou inštalátora na našich stránkach, bez potreby inštalácie ďalších nástrojov. Tento prístup by mohli používať firmy zaoberajúce sa vstavaným systémom (embeded systems), alebo elektrikári pri prototypovaní nových riešení.

### Ciele práce
1. Preskúmať, analyzovať a porovnať existujúce prístupy, softvérové aplikácie a knižnice využívané pri programovaní Arduino zariadení.
2. Preskúmať a analyzovať možnosti komponentového a udalosťami riadeného programovania s ohľadom na hardvérové obmedzenia Arduino zariadení.
3. Vychádzajúc z existujúcich open-source projektov a knižníc navrhnúť a implementovať uživateľsky prívetivé riešenie na jednoduché komponentovo-orientované a udalosťami riadené programovanie Arduino zariadení.
4. Implementovať vzorové komponenty využiteľné pri návrhu a implementácii IoT riešení.

#### Prezentácia zadania práce
- [Prezentácia (pdf)](/assets/DiplomovaPraca/prezentacia-pdsi1.pdf) *PDSI1*
- [Rozšírené zadanie (pdf)](/assets/DiplomovaPraca/rozsirene-zadanie-pdsi1.pdf) *PDSI1*
- [Prezentácia (pdf)](/assets/DiplomovaPraca/prezentacia-sdi1a.pdf) *SDI1a*
- [Prezentácia (pdf)](/assets/DiplomovaPraca/prezentacia-sdi1b.pdf
) *SDI1b*
- [Článok (pdf)](/assets/DiplomovaPraca/clanok-sdi1b.pdf) *SDI1b*

### Stav práce - dokončené úlohy
- Prieskum možností IOT zariadení
- Prieskum podobných riešení
- Návrh konfiguračných xml súborov a návrh kompilátora
- Návrh IDE pre naše riešenie
- Kompilátor konfiguračných xml pre mikrokontroler
- Implementované IDE pre naše riešenie
- Implementované základné vzorové komponenty
- Písanie a zveľaďovanie textu diplomovej práce
- Implementácia automatického dokončovania v editore zdrojového kódu
- Zverejnenie nového spôsobu vývoja ARDUINO komunite (testovanie)

### Arduino

Arduino je hardvér a softvér s otvoreným zdrojovým kódom, ktoré sú licencované na základe licencie GNPL Lesser General Public License (LGPL) aj GNU General Public License (GPL), umožňujúce výrobu dosiek Arduino a distribúciu softvéru každým. Arduino dosky sú komerčne dostupné v predmontovanej podobe alebo v súpravách do-it-yourself. *Viac sa dočítate v článku SDI1b.*

### Dostupné riešenia pre platformu Arduino
Stále rastúca komunita sa venuje zariadeniam Arduino. S tým je spojený aj vývoj rôznych frameworkov pre túto platformu, ktorých cieľom je zjednodušiť vývoj programátorom. Riešenia aké sme našli vyhľadávaním na fórach  Arduino komunity[10], rozdeľujeme do kategórií online a offline riešení. Online sú riešenia, ktoré do zariadenia nainštalujú zavádzač preposielajúci a vykonávajúci akcie len od servera (logika systému je len na serveri). Offline sú riešenia bežiace priamo na Arduino zariadení a na vykonanie akcie sa rozhodujú bez servera. Nižšie si povieme niečo viac o jednom online a dvoch offline riešeniach. *Viac sa dočítate v článku SDI1b.*

- Arduino EventManager
- Quantum Leaps Modeling Tool
- Cayenne

### Schéma nášho riešenia
V našom riešení bude programátor okrem ino súboru vytvárať aj xml súbor s popisom komponentov a udalostí. Z xml súboru budeme generovať knižnicu, ktorá bude importovaná zdrojovým súborom. Vygenerovaná knižnica bude obsahovať triedy komponentov, s ich inštanciami. Okrem toho bude obsahovať aj hlavné funkcie setup() aj loop(), v ktorých bude za programátora riešiť plánovanie spustenia udalostí. *Viac sa dočítate v článku SDI1b.*

![](/assets/DiplomovaPraca/acprog-scheme.png)

### Priebeh spracovania projektu

### Naše integrované vývojové prostredie
Pri snahe zachovať syntax a princípy programovania Arduino zariadení, sme sa rozhodli nevytvoriť úplne nový programovací jazyk. Vybrali sme sa smerom vytvorenia Arduino knižnice podľa popisu komponentov. Toto vytvorenie sa nazýva generovanie zdrojového kódu. Generátor dostáva na vstupe zoznam komponentov, kde komponenty majú určený typ (modul). *Viac sa dočítate v článku SDI1b.*

### Naše vývojové prostredie

![](/assets/DiplomovaPraca/ide-realne.png)

[GitHub projekt](https://github.com/acptools)

### Zoznam použitej literatúry
- [1] Doukas, C. Building internet of things with the arduino. ISBN: 978-14-700-23430.
- [2] Schwartz, M. Internet of things with arduino cookbook. ISBN: 978-17-852-86582.
- [3] Waher, P. Learning internet of things. ISBN: 978-17-835-5353-2.
- [4] The Arduino projects book, Second reprint, May 2013
- [5] Shvets, A. Design Patterns Explained Simply, ISBN:
- [6] Maurizio Gabbrielli, Simone Martini Programming Languages: Principles and Paradigms, ISBN: 9781848829145
- [7] <dependency><groupId>com.fifesoft</groupId><artifactId>rsyntaxtextarea</artifactId><version>2.6.1</version></dependency>
- [8] <dependency><groupId>sk.gbox.swing</groupId><artifactId>properties-panel</artifactId><version>0.0.2</version></dependency>
- [9] <dependency><groupId>org.dockingframes</groupId><artifactId>docking-frames-common</artifactId><version>1.1.1</version></dependency>
- [10] https://forum.arduino.cc/
- [11] https://www.arduino.cc/en/Products/Compare
- [12] https://github.com/igormiktor/arduino-EventManager
- [13] http://www.state-machine.com/products/#QM
- [14] https://mydevices.com/

### Demo projekt
Motivačným príkladom tejto práce je zariadenie zložená z tlačidla a led diódy. Led dióda má 1 sekundu svietiť a následne na 1 sekundu zhasnúť. Tlačidlo simuluje play/pause tlačidlo, na pozastavenie blikania led diódy. Nasledujúce súbory ukazujú implementáciu tohto príkladu v riešení navrhnutom touto prácou.\\
Nech priečinok Blink obsahuje nasledujúce súbory Blink.xml a Blink.ino.

**Blink.xml**
```
<?xml version="1.0" encoding="UTF-8" standalone="no"?>
<project platform="ArduinoUno">
 <components>
 <component>
 <name>blinkTimer</name>
 <type>acp.common.timer</type>
 <properties>
 <property name="Enabled">true</property>
 <property name="Interval">1000</property>
 </properties>
 <events>
 <event name="OnTick">onBlink</event>
 </events>
 </component>
 <component>
 <name>led</name>
 <type>acp.common.switch</type>
 <properties>
 <property name="Pin">13</property>
 <property name="InitialState">true</property>
 </properties>
 </component>
 <component>
 <name>button</name>
 <type>acp.common.digital_input_pin</type>
 <properties>
 <property name="ReadInterval">30</property>
 <property name="ReportOnState">false</property>
 <property name="Pin">2</property>
 <property name="ReportCyclesCount">33</property>
 <property name="PullupResistor">true</property>
 </properties>
 <events>
 <event name="OnStateChanged">buttonClicked</event>
 </events>
 </component>
 </components>
</project>
```

**Blink.ino**
```
//--------------------------------------------------------------------
// Includes required to build the sketch (including ext. dependencies)
#include <Blink.h>
//--------------------------------------------------------------------

void onBlink() {
 led.revert();
}

void buttonClicked() {
 if(button.getState() == HIGH) {
 if(blinkTimer.isEnabled()) {
 // Pause
 blinkTimer.disable();
 } else {
 // Play
 blinkTimer.enable();
 }
 }
}
```