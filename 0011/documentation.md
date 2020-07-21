# Co by se mohlo hodit?

## Co bude potřeba pro vylepšenou verzi

V jazyce C a C++ existují konstrukty, které se jmenují cykly (loops).

Existují 3 typy:

- for
- while
- do { ... } while

Pro tuto úlohu pravděpodobně použijete cyklus while. Ale pamatujte, že žádný z cyklů není špatně - experimentujte.

```
int vstup = 1;				// Definujeme promennou, do ktere budeme ukladat vstup od uzivatele
while (vstup == 1) {		// Obsah tela cyklu se bude opakovat dokud plati podminka ze vstup se rovna 1
     scanf("%d", &vstup);	// Nacteme cislo od uzivatele
}
		
printf("Zadal jste jine cislo nez 1.\n");
```
V této ukázce je nutné nastavit proměnnou vstup již před cyklem. Pokud bychom jí nenastavili, tak by v ní byla nedefinovaná hodnota. A tudíž při kontrole podmínky bychom dostávali náhodý výsledek.
Cykly `for` a `while` kontrolují podmíku již před jejich spuštění. Zatímoc cyklus `do {...} while`  jí kontroluje až po provdení těla.

```
 for ( ; 1 == 2 ; ) {
     printf("Tady nikdy nebudu, 1 se totiz nikdy nebude rovat 2.\n");
 }
 
 while (1 == 2) {
     printf("Tady taky nikdy nebudu.\n");
 }

 do {
     printf("Tady budu pouze 1. Pote se zkontroluje podminka a ukonci se cyklus.\n");
 } while (1 == 2);
```

Více informací o cyklech můžete získat:
- https://www.geeksforgeeks.org/loops-in-c-and-cpp/
- Dokumentace:
	- for: https://en.cppreference.com/w/c/language/for
	- while: https://en.cppreference.com/w/c/language/while
	- do { ... } while: https://en.cppreference.com/w/c/language/do


## Načítání vstupů

Pro načítání vstupů by mohla být použita funkce `scanf`, která je definována v knihovně `<stdio.h>`.

Něco o ní a jejím použití si můžete přečíst:
- přístupnější: https://www.geeksforgeeks.org/scanf-and-fscanf-in-c-simple-yet-poweful/

- oficiální dokumentace: https://en.cppreference.com/w/c/io/fscanf

Je vhodné si zjisti, jak funguje návratová hodnota této funkce, včetně možností čtení typů.

Příklad:
```
int num;
scanf("%d", &num ); // toto volání čte celé číslo a uloží jej do proměnné num
                    // návratová hodnota by zde měla být rovna 1 v případě,
                    // že se čtení povedlo (bylo načteno celé číslo)
                    // %d - znamená, že čteme proměnnou - celé číslo - integer
int num2, num3;
scanf("%d %d %d", &num, &num2, &num3 ); // návratová hodnota by měla být
                                        // v případě úspěšného čtení
                                        // rovna číslu 3
```

## Výpis na vstup

Pro výpis na standartní výstup by mohla být použita funkce `printf`, která je definována v knihově `<stdio.h>`.

Něco o ní a jejím použití si můžete přečíst:
- přístupnější: https://www.sallyx.org/sally/c/c07.php

- oficiální dokumentace: https://en.cppreference.com/w/cpp/io/c/fprintf

Je záhodno si zjistit, jak tato funkce funguje, včetně možností výpisu.

Příklad:

```
int num = 10;           // máme proměnnou typu integer - celé číslo
printf("%d\n", num);    // %d - znamená výpis celého čísla - digit / decimal
                        // toto vypíše obash proměnné "num", které je za čárkou
                        // \n - výpis nové řádky
int num2 = 11, num3 = 12;
printf("%d %d %d\n", num, num2, num3);  // vypíšeme tři integery v uvedeném
                                        // pořadí, všimněte si, že každé
                                        // %d, %s, %c... musí být doplněno 
                                        // o proměnnou, která by měla být
                                        // vypsána
```

# Proměnné

Bylo by si záhodno přečíst, jaké proměnné a datové typy jsou v jazyce C.

Materiály zde:
- proměnné: https://www.tutorialspoint.com/cprogramming/c_variables.htm

- datové typy: https://www.geeksforgeeks.org/data-types-in-c/

# Ostatní

- Předpokládáme, že nebudete používat nic z knihovny `<signal.h>` či `<csignal>` a nebudete se pouštět do ničeho z knihoven `<pthread.h>` či `<thread>`.

- Můžete používat jazyky C a C++. Pokud byste měli použít v C++ dynamickou alokaci, neměli byste obecně kombinovat ( maloc / free ) a ( new / delete ). Je to ve vašem vlastním zájmu. `Tato informace je spíše pro budoucí úkoly.`

- Náš program je ve fázi daleko v nedohlednu před alfa verzí. Pokud se budete snažit jí rozbít, povede se to. Mějte však na paměti, že vše běží na vašem počítači. Z naší strany žádná újma nehrozí, ale pokud se budete pokoušet o alokaci GB paměti, budete škodit jen sobě.

- Pokud budete potřebovat s čímkoli pomoci, obraťte se na administrátory verbálně či emailem v sekci About creators v hlavním menu.
