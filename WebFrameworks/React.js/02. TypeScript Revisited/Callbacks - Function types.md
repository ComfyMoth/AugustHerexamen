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
	console
}
```