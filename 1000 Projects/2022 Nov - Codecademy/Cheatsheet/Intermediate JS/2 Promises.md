---
created: Sunday, October 30th 2022 - 01.00
updated: Sunday, October 30th 2022 - 01.00
---
### States of a JS Promise
A JavaScript Promise object can be in one of three states: `pending`, `resolved`, or `rejected`.

While the value is not yet available, the `Promise` stays in the `pending` state. Afterwards, it transitions to one of the two states: `resolved` or `rejected`.

A `resolved` promise stands for a successful completion. Due to errors, the promise may go in the `rejected` state.

In the example code block, if the `Promise` is on `resolved` state, the first parameter holding a callback function of the `.then()` method will print the resolved value. Otherwise, an alert will be shown.

```js
const promise = new Promise((resolve, reject) => {
  const res = true;
  // An asynchronous operation.
  if (res) {
    resolve('Resolved!');
  }
  else {
    reject(Error('Error'));
  }
});

// Two arguments: .then(resolved, rejected)
promise.then((res) => console.log(res), (err) => alert(err));

// One arguments: .then(resolved) 
promise.then((res) => {
  console.log(value);
});

// Catch handle rejected
promise.catch((err) => {
  alert(err);
});
```

### JavaScript Promise.all()
```js
const promise1 = new Promise((resolve, reject) => {
  setTimeout(() => {
    resolve(3);
  }, 300);
});

const promise2 = new Promise((resolve, reject) => {
  setTimeout(() => {
    resolve(2);
  }, 200);
});

Promise.all([promise1, promise2]).then((res) => {
  console.log(res[0]);
  console.log(res[1]);
});
```

### setTimeout()
setTimeout() is an asynchronous JavaScript function that executes a code block or evaluates an expression through a callback function after a delay set in milliseconds.
```js
const loginAlert = () =>{
  alert('Login');
};

setTimeout(loginAlert, 6000);
```

### Avoiding nested Promise and .then()
```js
const promise = new Promise((resolve, reject) => {  
  setTimeout(() => {
    resolve('*');
  }, 1000);
});

const twoStars = (star) => {  
  return (star + star);
};

const oneDot = (star) => {  
  return (star + '.');
};

const print = (val) => {
  console.log(val);
};

// Chaining them all together
promise.then(twoStars).then(oneDot).then(print);
```

