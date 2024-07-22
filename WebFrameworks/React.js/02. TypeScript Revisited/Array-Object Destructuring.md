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
Hetzelfde concept kan je ook gebruiken bij objecten, in plaats van
```ts
interface Options {
	title: string;
	width?: number;
	height?: number;
}

let opties: Options = {
	title: "Menu"
	width: 100,
	height: 200
};

let title = options.title;
let width = options.width;
let height = options.height;
```
te doen kan je dit veel compacter schrijven aan de hand van **object destructuring**:
```ts
let opties : Options = {
title: "Menu",
width: 100,
height²: 200
};

let {title, width, height} = options;
```
De volgorde maakt hier ook niet uit zoland de namen maar overeenkomen met de keys van het object
```ts
let {width,title,height} = options;
```
mag dus ook

## Res