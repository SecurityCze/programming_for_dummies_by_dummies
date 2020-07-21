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
<h1> Systém pro detekci zásahů</h1>
<br>
Valve se rozhodlo, že by bylo dobré změnit fungování detekce zásahů do hráčů.
<br>
V praxi to funguje tak, že ne každý model, který je ve hře vidět, má přesně odpovídající hitbox ke svému modelu. Většinou se jedná o uskupení válců, koulí, krychlí a kvádrů (matematicky lehce popsatelné útvary).
<br>
My v této úloze budeme pracovat pouze se dvěma dimenzemi.
<br>
Poznámka autora: V této úloze si chci vyzkoušet, jak se vám bude pracovat s vícebodovým úkolem (tento úkol tedy bude rozdělen na několik částí, každá část je těžší něž předchozí a je nadstavbou předchozí části).
<br>
<h2> O co tedy jde?</h2>
<br>
<h3> [ Část 1 ]</h3>
<br>
Ilustrace: https://ctrlv.cz/MFkc
<br>
Program má za úkol detekovat zásahy do hráče. Pro zjednodušení se budeme pouze zabývat detekcí trupu a hlavy.
<br>
Program na začáku vypíše <span class="span-cls">Zadej souradnice hrace:</span>.
<br>
Program dostane od uživatele 4 páry souřadnic [ x , y ]:
<br>
<ul class="list-cls">
	<li class="list-item-cls">  První dvojice souřadnic reprezentuje hitbox <span class="span-cls">hlavy</span>.</li>	<li class="list-item-cls">  Druhá dvojice souřadnic reprezentuje hitbox <span class="span-cls">trupu</span>.</li>
</ul>

Pokud program úspěšně načte souřadnice, vypíše <span class="span-cls">Zadej souradnice kulek:</span>. V opačném případě vypíše <span class="span-cls">Nespravny vstup.</span>
<br>
Poté přijde další pár souřadníc, který reprezentuje kulku [ x , y ]:
<br>
<ul class="list-cls">
	<li class="list-item-cls">  Pokud trefí trup, znamená to udělení 25 poškození.</li>	<li class="list-item-cls">  Pokud trefí hlavu, znamená to udělení 50 poškození.</li>	<li class="list-item-cls">  Pokud kulka trefí hranici hlavy a těla, znamená to poškození jako u trefení hlavy.</li>	<li class="list-item-cls">  Pokud kulka netrefí cíl, znamená to MISS.</li>
</ul>

Program tedy vypíše jednu z následujících možností:
<br>
<ul class="list-cls">
	<li class="list-item-cls">  <span class="span-cls">Bullet check: 25 damage.</span></li>	<li class="list-item-cls">  <span class="span-cls">Bullet check: 50 damage.</span></li>	<li class="list-item-cls">  <span class="span-cls">Bullet check: MISS.</span></li>
</ul>

<h3> [ Část 2 ]</h3>
<br>
V této pokročilejší části se budeme zabývat tím, že program může obdržet více souřadnic kulek. Maximální počet není omezen, ale obdrží minimálně dvě.
<br>
Program tedy po každé kulce vypíše to, co minule, nakonec však připíše větu: <span class="span-cls">Total damage out of x bullets: y.</span>, kde x je nahrazeno počtem načtených kulek, a kde y je nahrazeno:
<br>
<ul class="list-cls">
	<li class="list-item-cls">  Součtem poškození.</li>	<li class="list-item-cls">  <span class="span-cls">MISS</span> v případě, že všechny kulky minuly.</li>
</ul>

Tento výpis bude tedy fungovat až u druhé zaznamenané kulky.
<br>
<h2> Co kontrolovat?</h2>
<br>
<ul class="list-cls">
	<li class="list-item-cls">  <span class="span-cls">I HRANA JE VALIDNÍ ZÁSAH</span></li>	<li class="list-item-cls">  souřadnice mohou být pouze nulové či kladné (toto je třeba kontrolovat), tzn. <span class="span-cls">musí to být kladné či nulové celé číslo</span></li>	<li class="list-item-cls">  nemusíte kontrolovat, zda se hlava napojuje na tělo (tzn. není třeba kontrolovat, zda je hlava oddělena), vždy to tak bude</li>	<li class="list-item-cls">  hlava a trup nikdy nebudou kolidovat, vždy budou napojeny jednou hranou</li>	<li class="list-item-cls">  není třeba kontrolovat, zda má hlava či trup nějaký objem, vždy bude mít</li>	<li class="list-item-cls">  je nutné kontrolovat dodržení struktury souřadnic, např. [ 10 , 10 ] je validní, [ 10 10 ] není</li>	<li class="list-item-cls">  můžete se spolehnou, že hlava bude vždy nad trupem, není možné dělat nějaké akrobatické kousky</li></ul>
