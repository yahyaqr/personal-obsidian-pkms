---
created: Sunday, October 30th 2022 - 01.21
updated: Sunday, October 30th 2022 - 01.21
---
### Resolving Javascript Promises
```js
function helloWorld() {
  return new Promise(resolve => {
    setTimeout(() => {
      resolve('Hello World!');
    }, 2000);
  });
}

const asyncFunction = async function() { //Async Function Expression
  const msg = await helloWorld();
  console.log('Message:', msg);
}

const asyncArrowFunction = async () => { //Async Arrow Function
  const msg = await helloWorld();
  console.log('Message:', msg);
}

asyncFunction(); // Message: Hello World! <-- after 2 seconds
asyncArrowFunction(); // Message: Hello World! <-- after 2 seconds
```

### Async Await Promises
```js
function helloWorld() {
  return new Promise(resolve => {
    setTimeout(() => {
      resolve('Hello World!');
    }, 2000);
  });
}

async function asyncFunction() {
  const msg = await helloWorld();
  console.log('Message:', msg);
}

asyncFunction(); // Message: Hello World! <-- after 2 seconds
```