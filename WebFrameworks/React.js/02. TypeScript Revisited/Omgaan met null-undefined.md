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

# Optional chaining
Stel dat we de interface iets aanpassen en de `width` en de `height` in een apart object plaatsen. Dan krijgen we de volgende situatie
```ts
interface Size {
	width: number;
	height: number;
}
interface Options {
	title: string;
	size: Size
}

let opties : Options = {
	title: 'Hello World',
	size: {
		width: 100,
		height: 100
	}
};

console.log(options.size.width); // 100
```

Als we nu `size` optioneel maken zoals hiervoor geraken in de problemen. Onze compiler zal ons dan de volgende foutmelding geven:
```ts
interface Size {
	width: number;
	height: number;
}
interface Options {
	title: string;
	size?: Size
}

let opties: Options = {
	title: 'Hello World',
	size: {
		width: 100,
		height: 100
	}
};

console.log(options.size.width) // Object is possibly 'undefined'
```

Omdat we `size` optioneel hebben gemaakt bestaat er een kans dat size undefined zou zijn. Dus de typescript compiler waarschuwt ons hiervoor. Hier kunnen we een aantal dingen aan doen. Je zou expliciet kunnen kijken of options.size gelijk is aan undefined aan de hand van een if statement:
```ts
let opties: Options = {
	title: 'Hello World'
};

if (options.size != undefined) {
	console.log(options.size.height);
}
```
of je kan hier optional chaining gebruiken. Je gebruikt hier ``