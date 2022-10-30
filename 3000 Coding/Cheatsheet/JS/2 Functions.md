### Named Function
```js
// Named Function
function rocketToMars() {
  return 'BOOM!';
}
```

### Anonymous Function
```js
// Anonymous Function
const rocketToMars = function() {
  return 'BOOM!';
}
```

### Function Expressions
```js
// Function Expressions
const dog = function() {
  return 'Woof!';
}
```

### Callback Functions
```js
const isEven = (n) => {
  return n % 2 == 0;
}

let printMsg = (evenFunc, num) => {
  const isNumEven = evenFunc(num);
  console.log(`The number ${num} is an even number: ${isNumEven}.`)
}

// Pass in isEven as the callback function
printMsg(isEven, 4); 
// Prints: The number 4 is an even number: True.
```
