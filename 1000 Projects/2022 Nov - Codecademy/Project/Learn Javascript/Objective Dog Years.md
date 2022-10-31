---
created: Saturday, October 29th 2022 - 19.01
updated: Saturday, October 29th 2022 - 19.01
---
```js
// Initial Value: My Age
const myAge = 22;

// Early Year
let earlyYears;
if (myAge >= 2) {
  earlyYears = 2;
} else {
  earlyYears = myAge;
}

// Multiplication 10.5
earlyYears *= 10.5;

// Later Year
let laterYears;
if (earlyYears >= 21) {
  laterYears = myAge - 2;
} else {
  laterYears = 0;
}

// Multiplication 4
laterYears *= 4;

// My Age in Dog Years
let myAgeInDogYears = earlyYears + laterYears;

// My Name
const myName = 'Yahya Aqrom'.toLowerCase();

// Log the result
console.log(`My name is ${myName}. I am ${myAge} years old in human years which is ${myAgeInDogYears} years old in dog years.\n`);


// Log the result
console.log('My early years equal to ' + earlyYears + ' dog years.');
console.log('My later years equal to ' + laterYears + ' dog years.');
```
