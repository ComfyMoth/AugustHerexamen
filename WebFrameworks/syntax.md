Spread = ...
- voorbeeld met Array:
```ts
let array : number[] = [1,2,3,4];
let newArray : number[] = array;

newArray.push(5);
console.log(array); // 1,2,3,4,5
console.log(newArray); // 1,2,3,4,5
```

- voorbeeld 2
```ts
let luna = {name: 'Luna Berry', age: 22}
let clone = {...luna};

clone.name = 'Clone Luna';

console.log(luna); // Luna Berry
console.log(clone); // Clone Berry
```