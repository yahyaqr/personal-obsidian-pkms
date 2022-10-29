---
created: Saturday, October 29th 2022 - 21.24
updated: Saturday, October 29th 2022 - 21.24
---
```js
let raceNumber = Math.floor(Math.random() * 1000);
let registerTime = Math.floor(Math.random() * 6) + 6;
let registeredEarly;
console.log(`Registering time: ${registerTime}.00 am\n`);

if (registerTime <= 9) {
  registeredEarly = true;
} else {
  registeredEarly = false;
}
const runnersAge = 24;

if (runnersAge >= 18 && registeredEarly) {
  raceNumber += 1000;
}

if (runnersAge > 18 && registeredEarly) {
  console.log(`Hello ${raceNumber}, you are registering early. Your race starts at 9.30 am.`);
} else if (runnersAge > 18 && !registeredEarly) {
  console.log(`Hello ${raceNumber}, you are registering late.  Your race starts at 11.00 am.`);
} else if (runnersAge < 18) {
  console.log(`Hello ${raceNumber}, Your race starts at 12.30 am.`);
} else {
  console.log(`Hello ${raceNumber}, please go to the registration desk.`);
}
```