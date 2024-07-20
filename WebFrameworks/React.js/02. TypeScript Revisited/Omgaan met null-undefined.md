# Optional
Soms heb je objecten waarbij niet alle properties een waarde hebben. In [[Typescript]] moet je dit aangeven in de interface van dat object. Stel dat we een `Options` interface hebben die gebruikt wordt om een scherm in te stellen.
```ts
interface Options {
	title: string;
	width: number;
	height: number;
}
```

Als je nu
```ts
let opties : Options = {
	title: 'Hello World'
};
// Type '(title: string;) is missing the following properties from type 'Options': width, height (2739)
```

doen dan krijg je een error in [[Typescript]] want width en height zijn hier niet opgegeven.

Wil je dit toch toelaten dan moet je dit aangeven in de interface van Options aan de hand van de ? operator. Dit geeft aan dat een property optional is.
```ts
interface Options {
	title: string;
	width?: number;
	height?: number;
}
```