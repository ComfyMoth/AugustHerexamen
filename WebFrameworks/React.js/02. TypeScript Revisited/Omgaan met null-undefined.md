# Optional
Soms heb je objecten waarbij niet alle properties een waarde hebben. In [[Typescript]] moet je dit aangeven in de interface van dat object. Stel dat we een `Options` interface hebben die gebruikt wordt om een scherm in te stellen.
```ts
interface Options {
	title: string;
	width: number;
	height: num
}
```