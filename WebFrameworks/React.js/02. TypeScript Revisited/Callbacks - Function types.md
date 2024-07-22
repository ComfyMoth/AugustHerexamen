Een callback is een functie (functie A) die wordt meegegeven als parameter van een andere functie (functie B). Deze functie (B) zal dan de meegegeven functie (A) uitvoeren.

Dit ziet er in code als volgt uit:
```ts
interface Callback {
	(): void
}

let functionA = (functionB: Callback) => {
	functionB();
}

let functionB: Callback = () => {
	console.log("Function B executed")
}

functionA(functionB);
```

Wil je geen interface aanmaken kan je ook gebruik maken van [[Typescript]] types rechtstreeks in de functie signature
```ts
let functionA = (functionB: () => void) => {
	functionB();
}
```

Een voorbeeld van zo'n callback functie kan je hieronder vinden
```ts
let sum = (a: number, b: number)
```