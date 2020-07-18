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
<b>scanf("%d", &num );</b><br>
<br>
<span style="color: green;">// toto volání čte celé číslo a uloží jej do proměnné num</span><br>
<span style="color: green;">// návratová hodnota by zde měla být rovna 1 v případě,</span><br>
<span style="color: green;">// že se čtení povedlo (bylo načteno celé číslo)</span><br>
<span style="color: green;">// %d - znamená, že čteme proměnnou - celé číslo - integer</span><br>
<br>
<b>int num2, num3;</b><br>
<b>scanf("%d %d %d", &num, &num2, &num3 );</b><br>
<span style="color: green;">// návratová hodnota by měla být</span><br>
<span style="color: green;">// v případě úspěšného čtení</span><br>
<span style="color: green;">// rovna číslu 3</span><br>
</div>

<h2> Výpis na výstup</h2>

Pro výpis na standartní výstup by mohla být použita funkce <span class="span-cls">printf</span>, která je definována v knihově <span class="span-cls">&lt;stdio.h&gt;</span>.

Něco o ní a jejím použití si můžete přečíst:
<ul class="list-cls">
	<li class="list-item-cls">  přístupnější: https://www.sallyx.org/sally/c/c07.php</li>
	<li class="list-item-cls">  oficiální dokumentace: https://en.cppreference.com/w/cpp/io/c/fprintf</li>
</ul>
Je záhodno si zjistit, jak tato funkce funguje, včetně možností výpisu.

Příklad:

<div class="block-cls">
<b>int num = 10;           </b><br>
<b>printf("%d\n", num);</b><br>
<span style="color: green;">// máme proměnnou typu integer - celé číslo</span><br>
<span style="color: green;">// %d - znamená výpis celého čísla - digit / decimal</span><br>
<span style="color: green;">// toto vypíše obash proměnné "num", které je za čárkou</span><br>
<span style="color: green;">// \n - výpis nové řádky</span><br>
<br>
<b>int num2 = 11, num3 = 12;</b><br>
<b>printf("%d %d %d\n", num, num2, num3);</b><br>
<span style="color: green;">// vypíšeme tři integery v uvedeném</span><br>
<span style="color: green;">// pořadí, všimněte si, že každé</span><br>
<span style="color: green;">// %d, %s, %c... musí být doplněno </span><br>
<span style="color: green;">// o proměnnou, která by měla být</span><br>
<span style="color: green;">// vypsána</span><br>
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
	<li class="list-item-cls">  Naše zpracování využívá výpis na chybový výstup <span class="span-cls">stderr</span>. Ten je vám tedy zapovězen. (Můžete ho sice použít, ale je možné, že něco rozbijete).</li>
	<li class="list-item-cls">  Předpokládáme, že nebudete používat nic z knihovny <span class="span-cls">&lt;signal.h&gt;</span> či <span class="span-cls">&lt;csignal&gt;</span> a nebudete se pouštět do ničeho z knihoven <span class="span-cls">&lt;pthread.h&gt;</span> či <span class="span-cls">&lt;thread&gt;</span>.</li>
	<li class="list-item-cls">  Můžete používat jazyky C a C++. Pokud byste měli použít v C++ dynamickou alokaci, neměli byste obecně kombinovat ( maloc / free ) a ( new / delete ). Je to ve vašem vlastním zájmu. <span class="span-cls">Tato informace je spíše pro budoucí úkoly.</span></li>
	<li class="list-item-cls">  Náš program je ve fázi daleko v nedohlednu před alfa verzí. Pokud se budete snažit jí rozbít, povede se to. Mějte však na paměti, že vše běží na vašem počítači. Z naší strany žádná újma nehrozí, ale pokud se budete pokoušet o alokaci GB paměti, budete škodit jen sobě.</li>
	<li class="list-item-cls">  Pokud budete potřebovat s čímkoli pomoci, obraťte se na administrátory verbálně či emailem v sekci About creators v hlavním menu.</li></ul>
