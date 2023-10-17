# Teorie

## Extrémní programování

> Extrémní programování je jednoduché, ale není snadné.

![XP Puzzle](/images/xp-puzzle.png)

## Párové programování

### Kritika

Nedává smysl psát všechen produkční kód v párech. Párové programování je příliš pomalé. Pár se spolu nemusí umět dohodnout, což může vést na spoustu neproduktivních diskuzí.

### Výhody

- real-time review kódu → méně chyb
- chyby jsou objeveny brzy → vývoj chybného kódu nepokračuje (ztráta času), ale chyba je opravena
- zlepšení kvality designu → může mít přímý vliv např. na rychlost vývoje!
- lepší řešení problému
- práce ve dvojici může vytvořit tlak na včasné doručení (člověk se neponoří do své komfortní zóny)
- lepší zaučení nových členů týmu
- větší uspokojení z práce
- čas k zamyšlení → neplýtvá se časem k vývoji něčeho, co později nebude potřeba
- projekt management: snížení rizika projektu

### Pravidla

- Párové programování není mentoring
- Jazyk je “my”
- Dlouhodobě je vhodné střídat páry
- Tvořit “spikes” jako přípravu na psaní produkčního kódu
- ? Je-li zavedeno code review, nemusíme psát všechen kód v páru


## Test-driven development

### Kritika

Nemá smysl psát všechny ty unit testy. Testy zaberou příliš mnoho času. Vývojáři nechtějí psát testy.

> Žádné unit-testy jsou lepší než špatné unit testy.
>
> --- Roy Osherove, The Art of Unit Testing


### Výhody

![Časová náročnost řešení chyby](/images/bug-detection.png)

--- Gerald Weinberg, Quality Software Management

### Pravidla

1. Produkční kód můžeš psát jen tehdy, když umožníš chybujícímu testu projít.
2. Nesmíš napsat více unit-testů než je nutné, aby testy selhaly.
3. Nesmíš napsat více kódu, než je nezbytné, aby jeden chybující unit-test prošel.

![TDD explained](/images/tdd-explained.webp)


### Pojmenovávání testů

Pojmenovávání testů: `MethodName_StateUnderTest_ExpectedBehaviour`

Příklady:
```
isAdult_AgeLessThan18_False
withdrawMoney_InvalidAccount_ExceptionThrown
admitStudent_MissingMandatoryFields_FailToAdmit
```

# Kata

Coding kata je cvičení na vývoj softwaru, při kterém není kladen důraz na řešení úkolu nebo problému,
ale na učení se novým dovednostem a vytváření úspěšných postupů.
U každé katy je třeba nalézt několik řešení, aby bylo možné poučit se z chyb, získat zkušenosti a vyvinout ještě lepší řešení.

## Prvočinitelé

Napište funkci, která rozkládá čísla složená na prvočinitele.

Například:
```
1 -> [] 
2 -> [2]
3 -> [3]
4 -> [2,2]
6 -> [2,3]
9 -> [3,3]
12 -> [2,2,3]
15 -> [3,5]
```

## FooBarQix

You should implement a function `String compute(Number)` which implements the following rules (one by one):

1. If the number is divisible by *3*, write *Foo* instead of the number
2. If the number is divisible by *5*, add *Bar*
3. If the number is divisible by *7*, add *Qix*
4. For each digit *3*, *5*, *7*, add *Foo*, *Bar*, *Qix* in the digits order.

Example:
```
1  => 1
2  => 2
3  => FooFoo (divisible by 3, contains 3)
4  => 4
5  => BarBar (divisible by 5, contains 5)
6  => Foo (divisible by 3)
7  => QixQix (divisible by 7, contains 7)
8  => 8
9  => Foo
10 => Bar
13 => Foo
15 => FooBarBar (divisible by 3, divisible by 5, contains 5)
21 => FooQix
33 => FooFooFoo (divisible by 3, contains two 3)
53 => BarFoo
60 => FooBar
```

## Diamant

Pro zadané písmeno vypište na obrazovku diamand začínající písmenem “A”. Zadané písmeno je v nejširším místě diamandu.

Například: printDiamond("C") vypíše:

```
  A
 B B
C   C
 B B
  A
```
