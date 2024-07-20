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
let clone = {...luna};

clone.name = 'Clone Luna';

console.log(luna); // Luna Berry
console.log(clone); // Clone Berry
```

Het is wel belangrijk dat je weet dat je hiermee enkel objecten kan kopiëren met 1 niveau diep
```ts
let address = { street: '123 fakestreet' };
let luna = { name: 'Luna Berry', age: 22, address: address };
let clone = {...luna}

clone.name = 'Clone Berry';
clone.address.street = '234 fakestreet';

console.log(luna.address.street); // 234 fakestreet
console.log(clone.address.street) // 234 fakestreet
```

Beide address velden wijzen naar hetzelfde object

Het kopiëren van objecten van meerdere niveau's diep noemen ze vaak een **'deep copy'** van het object. De beste manier om dit te doen is momenteel door eerst het object om te zetten naar een JSON-string en dan direct terug om te zetten naar een object:
```ts
let address = { street: '123 fakestreet' }
let luna = { name: 'Luna Berry', age: 37, address: address };
let clone = JSON.parse(JSON.stringify(luna));

clone.name = 'Clone Berry';
clone.address.street = '234 fakestreet'

console.log(luna.address.street); // 123 Fakestreet
console.log(clone.address.street); // 234 Fakestreet
```