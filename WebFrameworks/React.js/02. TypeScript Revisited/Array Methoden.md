Het is belangrijk om te weten dat in React.js bijna nooit gewone for lussen worden gebruikt. Het is vaak mogelijk om ze te gebruiken, maar het maakt de code bijna onleesbaar. Daarom is het kennen van array methoden een van de belangrijkste dingen die je moet kennen voordat je met React.js kan beginnen.

# Map
De map() functie maakt een nieuwe array bestaande uit de resultaten van de callback functie op elk elementen van die array. Deze functie is de meest gebruikte functie in React.js, dus zorg er voor dat je deze onder de knie hebt.

Wil je vb. een array van getallen omzetten naar een nieuwe array maar waar de elementen verdubbeld zijn, kunnen we dit op de volgende manier doen.
```ts
let numbers: number[] = [1,2,3,4,5];
let newArray: number[] = numbers.map(number => number * 2);
console.log(newArray);
```

Als we dit met een for lus zouden willen doen
```ts
let numbers: number[] = [1,2,3,4,5];
let newArray: number[] = [];
for (let number of numbers) {
	newArray.push(number*2);
}
console.log(newArray);
```
We verkiezen altijd in react.js voor de oplossing met de map functie.

# Filter
De filter