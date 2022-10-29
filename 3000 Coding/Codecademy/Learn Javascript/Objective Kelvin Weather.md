---
created: Saturday, October 29th 2022 - 18.42
updated: Saturday, October 29th 2022 - 18.42
---
```js
// Initial value: Kelvin
const kelvin = 283;

// Log the result
console.log(`The temperature is ${kelvin} degrees Kelvin.`);

// Convert kelvin to celcius
let celcius = kelvin - 273;

// Log the result
console.log(`The temperature is ${celcius} degrees Celcius.`);

// Convert celcius to fahrenheit
let fahrenheit = celcius * (9/5) + 32;

// Rounding down fahrenheit
fahrenheit = Math.floor(fahrenheit);

// Log the result
console.log(`The temperature is ${fahrenheit} degrees Fahrenheit.`);

// Convert celcius to newton
let newton = celcius * (33/100);

// Rounding down newton
newton = Math.floor(newton);

// Log the result
console.log(`The temperature is ${newton} degrees Newton`);
```
