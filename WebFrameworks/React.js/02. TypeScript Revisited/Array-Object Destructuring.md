Vaak willen we bepaalde delen van een object of array op een gemakkelijke manier aanspreken zonder dit uitdrukkelijk te doen aan de hand van de dot notatie (bij objecten) en de index (bij arrays)

# Array Destructuring
Zoals je weet kan je aan de hand van de array index bepaalde elementen aanspreken van een **array**:
```ts
// een array die een voornaam en achternaam bevat
let arr : string[] = ['Luna', 'Berry'];

let firstName = arr[0];
let lastName = arr[1];

console.log(firstName); // Luna
console.log(lastName); // Berry
```

Dit kan je ook schrijven als:
```ts
// een array die een voornaam en achternaam bevat
let arr: string[] = ['Luna', 'Berry'];

let [firstName, lastName] = arr;

console.log(firstName); // Luna
console.log(lastName); // Berry
```

Dit concept noemen we **Array destructuring**
Wil je bepaalde elementen overslagen dan kan je dit doen op de volgende manier:
```ts
let arr: string[] = ['Luna', 'Rosti', 'The Cutest', 'Of Belgium'];
let [firstName, title] = arr;

console.log(title); // The Cutest
```

Wil je vb. alleen de eerste twee waarden in een variabele en de rest in een nieuwe array kan je dit doen aan de hand van de `...` notatie:
```ts
let arr: string[] = ['Julius', 'Caesar', 'Consul', 'of the Roman Republic'];
let [firstName, lastName, ...rest] = arr;

console.log(firstName); // Julius
console.log(lastName); // Caesar
Console.log(rest); // ["Consul", "of the Roman Republic"]
```
De `rest` variabele bevat dan de array van de laatste twee elementen.

# Object Destructuring
