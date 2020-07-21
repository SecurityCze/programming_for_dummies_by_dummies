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
<h3> MMR systém</h3>
Valve se rozhodlo pro CS:GO vydat nový herní mód. A protože komunita dala jasně najevo, že je MMR systém nepřehledný odpad, Valve se s tím rozhodlo něco dělat. A od toho jsi tu ty.<br>
<br>
Nový mód bude probíhat stejně jako klasický kompetitivní mód. Rozdíl je, že každá hra bude trvat jen pět kol. (Such originality, much wow). Markeťáci se rozhodli, že nový MMR systém se bude jmenovat TotallyRetardedRatioSystem (TRRS).<br>
<br>
Program bude přijímat v každém kole statistiky jednoho týmu (tedy pěti hráčů) a na konci celého čtení (tedy po pěti kolech) přijme zda tým zvítězil či to totálně projebal - písmeno <span class="span-cls">w</span> (win) nebo písmeno <span class="span-cls">l</span> (prohra).<br>
<br>
<ul class="list-cls">
	<li class="list-item-cls">  První sloupec - zabití (kills): jedná se o celé číslo, může tedy být kladné, nulové či záporné. Musí však být z intervalu &lt;-5,5&gt; (protože hráč může zabít v jednom kole maximálně pět nepřátel a stejně tak může zabít 4 spojence a spáchat samovraždu).</li>
	<li class="list-item-cls">  Druhý sloupec - asisetnce (assists): jedná se o celé číslo které musí kladné či nulové, tedy z intervalu &lt;0,5&gt; (maximálně může hráč asistovat u zabití nepřátel, kterých je pět, damage do spojenců a z nich následná asisetence se do čísla nezapočítává). </li>
	<li class="list-item-cls">  Třetí sloupec - smrti (deaths): jedná se o celé číslo, které musí nabýt hodnoty nula či jedna.</li>
	<li class="list-item-cls">  Čtvrtý sloupec - MVP: jedná se o celé číslo, které musí nabýt hodnoty nula či jedna. V každém kole může být hodnota MVP rovna jedné nejvýše u jednoho hráče.</li>
<br>

</ul>
Stejně jako v kompetitivním zápase, i tady je za kolo možné maximálně pět killů pro tým (protože nepřátel je celkem pět) a to samé platí i u asistencí. Tím je také myšlena situace s nesprávným počtem zabití a asistencí dohromady (Hráč dá 4 fragy, ale má 2 asistence - není možné, protože zbyl jen jeden hráč k zabítí. Stejně je celkem 1 frag, ale hráč má více než jednu asistenci - toto je chyba.).<br>
Je možné dát za každého zabitého nepřítele nejvýše 4 asistence (program nedetekuje nutné poškození k asistenci, takže toto omezení odpadá. To bude muset implementovat jiný kolega :-) ).<br>
<br>
Právě tyto a výše zmíněné problémy musí program detekovat a v případě problému musí vypsat <span class="span-cls">Nespravny vstup</span> a ukončit se.<br>
<br>
Program na začátku musí vypsat hlášku pro uživatele: <span class="span-cls">Zadej herni vstupy:</span>.<br>
<br>
Finální logika rank-upu či rank-downu spočívá v magické formuli: <span class="span-cls">TRRS = sqrt( 3 * kills + assists + 2 * MVP - deaths )</span>.<br>
<br>
<ul class="list-cls">
	<li class="list-item-cls">  V případě, že by měla být provedena záporná odmocnina, je TRRS automaticky -1.</li>
	<li class="list-item-cls">  V případě, že TRRS je u hráče 2 a vyšší a tým vyhrál, program do konzole vypíše <span class="span-cls">Hrac #x: rank-up</span>.</li>
	<li class="list-item-cls">  V případě, že TRRS je u hráče 1.5 a nižší a tým prohrál, program do konzole vypíše <span class="span-cls">Hrac #x: rank-down</span>.</li>
	<li class="list-item-cls">  V jiném případě se do konzole jen vypíše <span class="span-cls">Hrac #x: 1.49</span>. 1.49 je jeho konečné TRRS vypsané na dvě místa.</li>
<br>

</ul>
<span class="span-cls">x</span> je nahrazeno pořadím hráče v tabulce (hráči nejsou řazeni podle TRRS či jiného předpokladu, zkrátka jsou seřazeni tak, jak byli nalogováni do hry).<br>
<br>
Zbytek viz. ukázkové běhy.<br>
