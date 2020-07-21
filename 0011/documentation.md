<style>
body {
	color: black;
	background-color: white;
}

.list-cls {

}

.list-item-cls {
	margin: 10px 0;
}

.span-cls {
	color: red;
}

.block-cls {
	padding: 4px;
	margin: 10px 0;
	border: 2px dashed black;
}
</style>
<h1> Co by se mohlo hodit?</h1>

<h2> Co bude potřeba pro vylepšenou verzi</h2>

V jazyce C a C++ existují konstrukty, které se jmenují cykly (loops).

Existují 3 typy:

<ul class="list-cls">
	<li class="list-item-cls">  for</li>	<li class="list-item-cls">  while</li>	<li class="list-item-cls">  do { ... } while</li>
</ul>
Pro tuto úlohu pravděpodobně použijete cyklus while. Ale pamatujte, že žádný z cyklů není špatně - experimentujte.

<div class="block-cls">
<b>int vstup = 1;				// Definujeme promennou, do ktere budeme ukladat vstup od uzivatele</b><br>
<b>while (vstup == 1) {		// Obsah tela cyklu se bude opakovat dokud plati podminka ze vstup se rovna 1</b><br>
<b>     scanf("%d", &vstup);	// Nacteme cislo od uzivatele</b><br>
<b>}</b><br>
<b>		</b><br>
<b>printf("Zadal jste jine cislo nez 1.\n");</b><br>
</div>
V této ukázce je nutné nastavit proměnnou vstup již před cyklem. Pokud bychom jí nenastavili, tak by v ní byla nedefinovaná hodnota. A tudíž při kontrole podmínky bychom dostávali náhodý výsledek.
Cykly <span class="span-cls">for</span> a <span class="span-cls">while</span> kontrolují podmíku již před jejich spuštění. Zatímoc cyklus <span class="span-cls">do {...} while</span>  jí kontroluje až po provdení těla.

<div class="block-cls">
<b> for ( ; 1 == 2 ; ) {</b><br>
<b>     printf("Tady nikdy nebudu, 1 se totiz nikdy nebude rovat 2.\n");</b><br>
<b> }</b><br>
<b> </b><br>
<b> while (1 == 2) {</b><br>
<b>     printf("Tady taky nikdy nebudu.\n");</b><br>
<b> }</b><br>
<br>
<b> do {</b><br>
<b>     printf("Tady budu pouze 1. Pote se zkontroluje podminka a ukonci se cyklus.\n");</b><br>
<b> } while (1 == 2);</b><br>
</div>

Více informací o cyklech můžete získat:
<ul class="list-cls">
	<li class="list-item-cls">  https://www.geeksforgeeks.org/loops-in-c-and-cpp/</li>	<li class="list-item-cls">  Dokumentace:</li></ul>
	- for: https://en.cppreference.com/w/c/language/for
	- while: https://en.cppreference.com/w/c/language/while
	- do { ... } while: https://en.cppreference.com/w/c/language/do


<h2> Načítání vstupů</h2>

Pro načítání vstupů by mohla být použita funkce <span class="span-cls">scanf</span>, která je definována v knihovně <span class="span-cls">&lt;stdio.h&gt;</span>.

Něco o ní a jejím použití si můžete přečíst:
<ul class="list-cls">
	<li class="list-item-cls">  přístupnější: https://www.geeksforgeeks.org/scanf-and-fscanf-in-c-simple-yet-poweful/</li>
	<li class="list-item-cls">  oficiální dokumentace: https://en.cppreference.com/w/c/io/fscanf</li>
</ul>
Je vhodné si zjisti, jak funguje návratová hodnota této funkce, včetně možností čtení typů.

Příklad:
<div class="block-cls">
<b>int num;</b><br>
<b>scanf("%d", &num ); // toto volání čte celé číslo a uloží jej do proměnné num</b><br>
<b>                    // návratová hodnota by zde měla být rovna 1 v případě,</b><br>
<b>                    // že se čtení povedlo (bylo načteno celé číslo)</b><br>
<b>                    // %d - znamená, že čteme proměnnou - celé číslo - integer</b><br>
<b>int num2, num3;</b><br>
<b>scanf("%d %d %d", &num, &num2, &num3 ); // návratová hodnota by měla být</b><br>
<b>                                        // v případě úspěšného čtení</b><br>
<b>                                        // rovna číslu 3</b><br>
</div>

<h2> Výpis na vstup</h2>

Pro výpis na standartní výstup by mohla být použita funkce <span class="span-cls">printf</span>, která je definována v knihově <span class="span-cls">&lt;stdio.h&gt;</span>.

Něco o ní a jejím použití si můžete přečíst:
<ul class="list-cls">
	<li class="list-item-cls">  přístupnější: https://www.sallyx.org/sally/c/c07.php</li>
	<li class="list-item-cls">  oficiální dokumentace: https://en.cppreference.com/w/cpp/io/c/fprintf</li>
</ul>
Je záhodno si zjistit, jak tato funkce funguje, včetně možností výpisu.

Příklad:

<div class="block-cls">
<b>int num = 10;           // máme proměnnou typu integer - celé číslo</b><br>
<b>printf("%d\n", num);    // %d - znamená výpis celého čísla - digit / decimal</b><br>
<b>                        // toto vypíše obash proměnné "num", které je za čárkou</b><br>
<b>                        // \n - výpis nové řádky</b><br>
<b>int num2 = 11, num3 = 12;</b><br>
<b>printf("%d %d %d\n", num, num2, num3);  // vypíšeme tři integery v uvedeném</b><br>
<b>                                        // pořadí, všimněte si, že každé</b><br>
<b>                                        // %d, %s, %c... musí být doplněno </b><br>
<b>                                        // o proměnnou, která by měla být</b><br>
<b>                                        // vypsána</b><br>
</div>

<h1> Proměnné</h1>

Bylo by si záhodno přečíst, jaké proměnné a datové typy jsou v jazyce C.

Materiály zde:
<ul class="list-cls">
	<li class="list-item-cls">  proměnné: https://www.tutorialspoint.com/cprogramming/c_variables.htm</li>
	<li class="list-item-cls">  datové typy: https://www.geeksforgeeks.org/data-types-in-c/</li>
</ul>
<h1> Ostatní</h1>

<ul class="list-cls">
	<li class="list-item-cls">  Předpokládáme, že nebudete používat nic z knihovny <span class="span-cls">&lt;signal.h&gt;</span> či <span class="span-cls">&lt;csignal&gt;</span> a nebudete se pouštět do ničeho z knihoven <span class="span-cls">&lt;pthread.h&gt;</span> či <span class="span-cls">&lt;thread&gt;</span>.</li>
	<li class="list-item-cls">  Můžete používat jazyky C a C++. Pokud byste měli použít v C++ dynamickou alokaci, neměli byste obecně kombinovat ( maloc / free ) a ( new / delete ). Je to ve vašem vlastním zájmu. <span class="span-cls">Tato informace je spíše pro budoucí úkoly.</span></li>
	<li class="list-item-cls">  Náš program je ve fázi daleko v nedohlednu před alfa verzí. Pokud se budete snažit jí rozbít, povede se to. Mějte však na paměti, že vše běží na vašem počítači. Z naší strany žádná újma nehrozí, ale pokud se budete pokoušet o alokaci GB paměti, budete škodit jen sobě.</li>
	<li class="list-item-cls">  Pokud budete potřebovat s čímkoli pomoci, obraťte se na administrátory verbálně či emailem v sekci About creators v hlavním menu.</li></ul>
