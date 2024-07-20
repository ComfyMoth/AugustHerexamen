# Spread operator
je zou *denken* dat volgende code een kopie van een array maakt:
```ts
let array : number[] = [1,2,3,4];
let NewArray : number[] = array;
```

Maar dat werkt niet! Hierboven wordt gewoon de referentie naar `array` toegewezen aan de variabele `newArray`. `array` en `newArray` verwijzen gewoon naar dezelfde plaats in het geheugen. Het onderstaande voorbeeld toont dit aan:
```ts
let array : number[] = [1,2,3,4];
let newArray : number[] = array;

newArray.push(5);
console.log(array); // 1,2,3,4,5
console.log(newArray); // 1,2,3,4,5
```

Als je een kopie van een array moet maken dan ga je gebruik moeten maken van de <span style="color:#c8ab83;">spread</span> syntax (drie puntjes)
```ts
let array : number[] = [1,2,3,4]
let newArray : number[] = [...array];

newArray.push(5);
console.log(array); // 1,2,3,4
console.log(newArray); // 1,2,3,4,5
```

Beide verwijzen nu naar een aparte plaats in het geheugen

# Objecten kopiëren
Het bovenstaande geldt ook voor objecten:
*deze code werkt niet*
```ts
let luna = { name: 'Luna Berry', age: 22 };
let clone = luna;

clone.name = 'Clone Berry'

console.log(luna); //Clone Berry
console.log(clone); //Clone Berry
```

*deze code gebruikt de spread syntax en werkt dus wel*
```ts
let luna = {name: 'Luna Berry', age: 22}
let clone = {...}
```