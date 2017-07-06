## Úvod do jazyka Kotlin

[Jazyk Kotlin](https://kotlinlang.org) je pomerne mladý jazyk, ktorý vznikol na základe jazyka Java, aby sa dali medzi sebou ľahko nahrádzať. Hovoríme aj, aby boli navzájom kompatibilné.

Je to moderný programovací jazyk, ktorý je

- Jednotný (konzistentný) – je vždy jasné, čo je zapísané
- Bezpečný – pri práci sa robí menej chýb, ako pri práci s Javou
- Medzioperačný – dá sa používať všade tam, kde Java: server, Android, …
- Dá sa programovať v rôznych nástrojoch

### Vývojové prostredie

Na základnú prácu a spoznanie sa s jazykom Kotlin budeme používať softvér, ktorý je zadarmo a volá sa [IntelliJ IDEA](https://www.jetbrains.com/idea/). Ten si treba stiahnuť a otvoriť, aby sme mohli začať.

### Vytvorenie nového projektu v IntelliJ IDEA

V IntelliJ IDEA potrebujeme po spustení urobiť pár základných úkonov, aby sme mohli napísať prvý program v jazyku Kotlin.

[![New Project](/images/NewProject.png)](images/NewProject.png)

1. Ako **Project SDK** vybrať konkrétnu verziu Javy, ktorá by v IntelliJ IDEA mala byť už doinštalovaná.
2. V časti **Additional Libraries and Frameworks** zaškrtnúť voľbu **Kotlin (Java)**
3. **Use Library** by malo obsahovať *KotlinJavaRuntime*
4. **Next**

Ďalším krokom je výber šablóny. Tento krok teraz preskakujeme, vôbec nás nezaujíma, nakoľko začneme s jazykom Kotlin *na čistom papieri*, ako sa hovorí.

[![Choose Template](images/Template.png)](images/Template.png)

Zadáme **Next**.

[![Project Name](images/Name.png)](images/Name.png)

V ďalšom kroku zadáme meno nového projektu. V ukážke to je **Hello World** a zadáme **Finish**.

### Nastavenie projektu

Teraz sa otvorí obrazovka projektu *Hello World*.

[![Project](images/Project.png)](images/Project.png)

Teraz je dôležité nastaviť jazyk Kotlin v projekte pomocou **Tools > Kotlin > Configure Kotlin in Project > All modules containing Kotlin files**. Zvyšok ponecháme tak, ako je a potvrdíme **OK**.

[![Configure Kotlin](images/ConfigureKotlin.png)](kotlin/images/ConfigureKotlin.png)

### Štruktúra projektu

Zatiaľ nás bude zaujímať zo štruktúry projektu zložka `/src/`.

[![Src](images/Src.png)](images/Src.png)

Vyznačíme ju a klikneme pravým tlačidlom. Po zobrazení ponuky vyberieme `New > Kotlin File/Class`.

[![Kotlin File](images/KotlinFile.png)](images/KotlinFile.png)

Potom zadáme meno nového súboru, napr. **HelloWorld** a potvrdíme **OK**.

[![File Name](images/FileName.png)](images/FileName.png)

IntelliJ IDEA teraz pripraví a otvorí nový súbor na úpravu.

[![Edit new file](images/EditFile.png)](images/EditFile.png)

## Prvý program

V otvorenom súbore **HelloWorld.kt** napíšeme `main` a stlačíme tabulátor.

![Main Function](screencasts/mainFunction.gif)

IntelliJ IDEA automaticky doplní hlavnú funkciu, do ktorej budeme písať akýkoľvek program v začiatkoch. Nebudeme sa teraz zaoberať, čo je funkcia, prečo sa táto volá `main`, ani čo je to tam popísané. Momentálne nám pôjde o to, čo bude v zložených zátvorkách `{}`.

![Body of the Main Function](screencasts/bodyOfMainFunction.gif)

Aby sme ten prvý program skúsili, do spomínaných zložených zátvoriek napíšeme tento príkaz:

```kotlin
println("Toto je môj prvý program v jazyku Kotlin!")
```

Funkcia `main` bude vyzerať nasledovne:

```kotlin
fun main(args: Array<String>) {
    println("Toto je môj prvý program v jazyku Kotlin!")
}
```

Pre spustenie programu pravým tlačidlom klikneme do programu, ktorý sme práve napísali a vyberiem **Run HelloWorldKt**.

![Run program](screencasts/runProgram.gif)

Výsledok vidíme v dolnej časti, v tzv. konzole.

[![Console](images/Console.png)](images/Console.png)

Kde sa vypísal text *Toto je môj prvý program v jazyku Kotlin!*

[![Console](images/Console2.png)](images/Console2.png)

O funkcii `println()` si povieme viac neskôr.

## Základné dátové typy

Pri programovaní budeme vždy pracovať s typmi údajov. V bežnom živote sa môžeme stretnúť s číslami, s textami a podobne. V jazyku Kotlin to je podobné a zo začiatku budeme rozlišovať tri jednoduché dátové typy: **textové reťazce** (`String`), **celé** čísla (`Int`), **reálne čísla** (`Double`).

### Int

Celé čísla sú jednoduché na rýchle pochopenie. Píšu sa bez desatinnej bodky. Skúsme do funkcie `main` napísať tento zdrojový kód:

```kotlin
println(3 + 4)
```

Funkcia `main` bude teda vyzerať takto:

```kotlin
fun main(args: Array<String>) { 
    println(3 + 4)
}
```

Keď program spustíme, výsledok bude vypísaný do konzoly, výsledok bude **7**. Rovnakým spôsobom sa dajú robiť akékoľvek základné matematické operácie.

### Double

Reálne čísla sa zapisujú s desatinnou bodkou. Skúsme napr.:

```kotlin
fun main(args: Array<String>) { 
    println(2.9 + 4.1)
}
```

Výsledok bude **7.0**.

Rozdiel medzi celým a reálnym číslom v programovacom jazyku Kotlin je dosť podstatný. Náš mozog tie čísla berie za rovnaké, pre počítače sú však odlišné a inak k nim musíme pristupovať. Napr. pri celočíselnom delení so zvyškom musíme byť v tomto veľmi opatrní.

### String

Ďalším jednoduchým typom sú reťazce. S nimi sme sa stretli pri prvej ukážke. Každý reťazec sa totiž zapisuje do úvodzoviek. Keď ho chceme vypísať do konzoly, použijeme takýto zápis:

```kotlin
println("Toto je super reťazec 3000!")
```

Všetko, čo je uzavreté do úvodzoviek sa chápe ako reťazec, čiže usporiadná množina znakov. Uvedené číslo 3000 je v tomto príklade pre jazyk Kotlin tiež reťazec, nie číslo.

Spustenie tohto programu vypíše text „**Toto je super reťazec 3000!**“.

## Konštanty

Keď chceme uchovávať nejakú hodnotu, napr. číslo 3,14 a používať ju v programe na viacerých miestach bez toho, aby sme si túto hodnotu museli pamätať alebo neustále zapisovať, použijeme konštantu. Definuje sa takto:

```kotlin
val pi = 3.1415
```

Definícia začína vyhradeným slovom `val`, za ktorým ide vlastné meno, ktoré určujeme my. Potom spravidla nasleduje znamienko rovná sa `=` a za ním hodnota, ktorú táto konštanta nadobúda.

Keď chceme vypočítať obvod kruhu, použitie konštánt bude nasledovné:

```kotlin
fun main(args: Array<String>) {
    val pi = 3.1415
    val r = 4.0
    val perimeter = 2 * pi * r
    println("Obvod kruhu s polomerom $r je $perimeter.")
}
```

### Definovanie typu

Definovanie konštanty vieme uskutočniť aj riadnym určeným typu. Napríklad pre vyššie definovanú konštantú **pí** to bude takto:

```kotlin
val pi: Double = 3.1415
```

Za meno konštanty zadáme dvojbodku a za ňou meno typu, v tomto prípade `Double`.

Rovnako sa určuje aj typ `Int` alebo `String`. Napríklad:

```kotlin
val retazec: String = "Toto je konštanta typu String"
val celeCislo: Int = 42
```

Konštanty sa preto volajú konštanty, lebo sú **konštantné** a nemôžu sa meniť. Čiže ak už máme konštantu `celeCislo` rovnú hodnote 42, neskôr v programe nemôžeme urobiť nové priradenie:

```kotlin
celeCislo = 43
```

Program potom zahlási chybu a nespustí sa.

## Premenné

Aby sme mohli meniť hodnoty, máme premenné, ktoré sa volajú premennými preto, že sa dajú **premeniť**.

## Reťazce

## Podmienky

## Polia, zoznamy a cykly

## Funkcie (metódy)

## Objekty a triedy
