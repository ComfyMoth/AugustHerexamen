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
let arr: string[] = ['Luna', 'Rosti', 'The Cutest', 'Of'];

```