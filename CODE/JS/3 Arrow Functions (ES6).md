### Arrow function with no arguments
```js
const printHello = () => { 
  console.log('hello'); 
}; 
printHello(); // Prints: hello
```

### Arrow function with single argument
Arrow functions with a single parameter do not require () around the parameter list.
```js
const checkWeight = weight => { 
  console.log(`Baggage weight : ${weight} kilograms.`); 
}; 
checkWeight(25); // Prints: Baggage weight : 25 kilograms.
```

### Arrow function with two argument
```js
const sum = (firstParam, secondParam) => { 
  return firstParam + secondParam; 
}; 
console.log(sum(2,5)); // Prints: 7 
```

### Concise Arrow Function
Arrow functions with a single expression can use the concise function body which returns the result of the expression without the return keyword.
```js
const multiply = (a, b) => a * b; 
console.log(multiply(2, 30)); // Prints: 60 
```
