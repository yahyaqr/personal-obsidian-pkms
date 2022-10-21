### Built-in Properties
```js
//Assign a function to a variable originalFunc
const originalFunc = num => num + 2;

//Re-assign the function to a new variable newFunc
const newFunc = originalFunc;

//Access the function's name property
newFunc.name; //'originalFunc'

//Return the function's body as a string
newFunc.toString(); //'(num) => { return num + 2 }'

console.log(newFunc.name);
console.log(newFunc.toString());
```

### Add our own properties
```js
const originalFunc = num => num + 2;
const newFunc = originalFunc;

//Add our own isMathFunction property to the function
newFunc.isMathFunction = true;

console.log(newFunc.isMathFunction);
```

### The .reduce() method
```js
const arrayOfNumbers = [1, 2, 3, 4];

const sum = arrayOfNumbers.reduce((accumulator, currentValue) => {  
  return accumulator + currentValue;
});

console.log(sum); // 10
```

### The .forEach() method
```js
const numbers = [28, 77, 45, 99, 27];

numbers.forEach(number => {  
  console.log(number);
});
```

### The .filter() method
```js
const randomNumbers = [4, 11, 42, 14, 39];
const filteredArray = randomNumbers.filter(n => {  
  return n > 5;
});
```

### The .map() method
```js
const finalParticipants = ['Taylor', 'Donald', 'Don', 'Natasha', 'Bobby'];

// add string after each final participant
const announcements = finalParticipants.map(member => {
  return member + ' joined the contest.';
})

console.log(announcements);
```