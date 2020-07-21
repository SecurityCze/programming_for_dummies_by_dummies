# Systém pro detekci zásahů

Valve se rozhodlo, že by bylo dobré změnit fungování detekce zásahů do hráčů.

V praxi to funguje tak, že ne každý model, který je ve hře vidět, má přesně odpovídající hitbox ke svému modelu. Většinou se jedná o uskupení válců, koulí, krychlí a kvádrů (matematicky lehce popsatelné útvary).

My v této úloze budeme pracovat pouze se dvěma dimenzemi.

Poznámka autora: V této úloze si chci vyzkoušet, jak se vám bude pracovat s vícebodovým úkolem (tento úkol tedy bude rozdělen na několik částí, každá část je těžší něž předchozí a je nadstavbou předchozí části).

## O co tedy jde?

### [ Část 1 ]

Ilustrace: https://ctrlv.cz/MFkc

Program má za úkol detekovat zásahy do hráče. Pro zjednodušení se budeme pouze zabývat detekcí trupu a hlavy.

Program na začáku vypíše `Zadej souradnice hrace:`.

Program dostane od uživatele 4 páry souřadnic [ x , y ]:

- První dvojice souřadnic reprezentuje hitbox `hlavy`.
- Druhá dvojice souřadnic reprezentuje hitbox `trupu`.

Pokud program úspěšně načte souřadnice, vypíše `Zadej souradnice kulek:`. V opačném případě vypíše `Nespravny vstup.`

Poté přijde další pár souřadníc, který reprezentuje kulku [ x , y ]:

- Pokud trefí trup, znamená to udělení 25 poškození.
- Pokud trefí hlavu, znamená to udělení 50 poškození.
- Pokud kulka trefí hranici hlavy a těla, znamená to poškození jako u trefení hlavy.
- Pokud kulka netrefí cíl, znamená to MISS.

Program tedy vypíše jednu z následujících možností:

- `Bullet check: 25 damage.`
- `Bullet check: 50 damage.`
- `Bullet check: MISS.`

### [ Část 2 ]

V této pokročilejší části se budeme zabývat tím, že program může obdržet více souřadnic kulek. Maximální počet není omezen, ale obdrží minimálně dvě.

Program tedy po každé kulce vypíše to, co minule, nakonec však připíše větu: `Total damage out of x bullets: y.`, kde x je nahrazeno počtem načtených kulek, a kde y je nahrazeno:

- Součtem poškození.
- `MISS` v případě, že všechny kulky minuly.

Tento výpis bude tedy fungovat až u druhé zaznamenané kulky.

## Co kontrolovat?

- `I HRANA JE VALIDNÍ ZÁSAH`
- souřadnice mohou být pouze nulové či kladné (toto je třeba kontrolovat), tzn. `musí to být kladné či nulové celé číslo`
- nemusíte kontrolovat, zda se hlava napojuje na tělo (tzn. není třeba kontrolovat, zda je hlava oddělena), vždy to tak bude
- hlava a trup nikdy nebudou kolidovat, vždy budou napojeny jednou hranou
- není třeba kontrolovat, zda má hlava či trup nějaký objem, vždy bude mít
- je nutné kontrolovat dodržení struktury souřadnic, např. [ 10 , 10 ] je validní, [ 10 10 ] není
- můžete se spolehnou, že hlava bude vždy nad trupem, není možné dělat nějaké akrobatické kousky
