# Spread operator
je zou *denken* dat volgende code een kopie van een array maakt:
```ts
let array : number[] = [1,2,3,4];
let NewArray : number[] = array;
```

Maar dat werkt niet! Hierboven wordt gewoon de referentie naar `array` toegewezen aan de variabele `newArray`. `array` en `newArray` verwijzen gewoon naar dezelfde plaats