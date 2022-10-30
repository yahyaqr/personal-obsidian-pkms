---
created: Sunday, October 30th 2022 - 01.45
updated: Sunday, October 30th 2022 - 01.45
---
### ReferenceError

### SyntaxError

### TypeError

### The throw Keywor in JS
```js
// The program will raise and output this Error object with message 'Something went wrong'
throw Error('Something went wrong');

//The program will stop running after an error has been raised, and any following code will not be executed.
console.log('This will not be printed');
```

### JS Error Function
```js
console.log(Error('Your password is too weak.')); //Error: Your password is too weak.
```

### JS Try Catch
```js
// A try...catch statement that throws a constructed Error()
try {
  throw Error('This constructed error will be caught');
} catch (e) {
  console.log(e); // Prints the thrown Error object
}

// A try...catch statement that throws a built-in error
const fixedString = 'Cannot be reassigned';
try {
  fixedString = 'A new string'; // A TypeError will be thrown  
} catch (e) {
  console.log('An error occurred!'); // Prints 'An error occurred!'
}

console.log('Prints after error'); // Program continues running after the error is handled and prints 'Prints after error'
```