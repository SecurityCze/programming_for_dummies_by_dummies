# Žádosti na vylepšéní od Valve support teamu

## Problém

V minulých dnech jste úspěšně deploynuli program pro podporu Valve support teamu. Tato aplikace dovolila teamu vyřídit všechny čekající tickety.

Bohužem z důvodu světové pandemie virem COVID-2019 došlo k uzavření Indického support centra. A je potřeba zvýšit efektivitu zpracování ticketů.

Po dlouhé a drahé studii bylo zjištěna průměrná doba vyřízení 1 ticketu: 4,25 sekundy. To je nepřijatelné.

Je tedy nutné vylepšit dosavadní systém, a to v 3 bodech:

	1) Z důvodu nekompatibility některých systému upoušťíme od používání háčků a čárek. (Všechna tato písmena budou nahrazena verzí bez diakritiky)

	2) Přidáváme novou kategorii dotazu: `0` s generovanou odpovědí: `Dekujeme, tento problem byl vyresen.`
	
	3) Program načítá kategorie a vypisuje odpověďi do prvního chybného vstupu. Poté vypíše `ERROR` a ukončí se.

## Program

Jedná se o upgrade podpůrného programu ze Zahřívací úlohy. Jecho chování je následující:

Program vypíše `Kategorie dotazu?` a čeká na vstup od uživatele.

Na vstupu programu bude číselná hodnota 0-3. Tato hodnota představuje kategorii problému. Program poté podle kategorie vypíše automatickou odpověď uživateli (viz ukázka běhu).

V případě že na vstupu programu bude neplatný vstup (prázdný vstup, neznáme číslo, jiný znak...) vypíše program chybové hlášení a ukončí se. 

Program opět vypíše dotaz a pokračuje v načítání.

## Co kontrolovat?

- Všechny výpisy programu jsou ukončeny novou řádkou.	
- A program ignoruje bílé znaky (mezera, nový řádek...).

