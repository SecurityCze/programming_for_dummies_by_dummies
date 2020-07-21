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
<h1> Žádosti na vylepšení od Valve support teamu</h1>
<br>
<h2> Problém</h2>
<br>
V minulých dnech jste úspěšně deploynuli program pro podporu Valve support teamu. Tato aplikace dovolila teamu vyřídit všechny čekající tickety.
<br>
Bohužem z důvodu světové pandemie virem COVID-2019 došlo k uzavření Indického support centra. A je potřeba zvýšit efektivitu zpracování ticketů.
<br>
Po dlouhé a drahé studii bylo zjištěna průměrná doba vyřízení 1 ticketu: 4,25 sekundy. To je nepřijatelné.
<br>
Je tedy nutné vylepšit dosavadní systém, a to v 3 bodech:
<br>
<ul class="list-cls">
	<li class="list-item-cls">  1 =&gt; Z důvodu nekompatibility některých systému upoušťíme od používání háčků a čárek. (Všechna tato písmena budou nahrazena verzí bez diakritiky)</li>	<li class="list-item-cls">  2 =&gt; Přidáváme novou kategorii dotazu: <span class="span-cls">0</span> s generovanou odpovědí: <span class="span-cls">Dekujeme, tento problem byl vyresen.</span></li>	<li class="list-item-cls">  3 =&gt; Program načítá kategorie a vypisuje odpověďi do prvního chybného vstupu. Poté vypíše <span class="span-cls">ERROR</span> a ukončí se.</li>
</ul>

<h2> Program</h2>
<br>
Jedná se o upgrade podpůrného programu ze Zahřívací úlohy. Jecho chování je následující:
<br>
Program vypíše <span class="span-cls">Kategorie dotazu?</span> a čeká na vstup od uživatele.
<br>
Na vstupu programu bude číselná hodnota 0-3. Tato hodnota představuje kategorii problému. Program poté podle kategorie vypíše automatickou odpověď uživateli (viz ukázka běhu).
<br>
V případě že na vstupu programu bude neplatný vstup (prázdný vstup, neznáme číslo, jiný znak...), vypíše program chybové hlášení a ukončí se. 
<br>
Program opět vypíše dotaz a pokračuje v načítání.
<br>
<h2> Co kontrolovat?</h2>
<br>
<ul class="list-cls">
	<li class="list-item-cls">  Všechny výpisy programu jsou ukončeny novou řádkou.	</li>	<li class="list-item-cls">  A program ignoruje bílé znaky (mezera, nový řádek...).</li>
</ul>

