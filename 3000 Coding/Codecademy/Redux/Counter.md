---
created: Sunday, October 30th 2022 - 23.23
updated: Sunday, October 30th 2022 - 23.23
---
```js
/* Note to learners: 
Normally, you would import redux like this:

  import { createStore } from 'redux';

Due to Codecademy's technical limitations 
for testing this exercise, we are using 
`require()`.
*/
const { createStore } = require('redux');

// Action Creators
function increment() { 
  return {type: 'increment'}
}

function decrement() { 
  return {type: 'decrement'}
}

// Reducer / Store
const initialState = 0;
const countReducer = (state = initialState, action) => {
  switch (action.type) {
    case 'increment':
      return state + 1; 
    case 'decrement':
      return state - 1; 
    default:
      return state;
  }
};  
const store = createStore(countReducer);

// HTML Elements
const counterElement = document.getElementById('counter');
const incrementer = document.getElementById('incrementer');
const decrementer = document.getElementById('decrementer');

// Store State Change Listener

const render = () => {
  counterElement.innerHTML = store.getState();
}
store.subscribe(render);
render();

// DOM Event Handlers
const incrementerClicked = () => {
  store.dispatch(increment());
}
incrementer.addEventListener('click', incrementerClicked);
 
const decrementerClicked = () => {
  store.dispatch(decrement());  
}
decrementer.addEventListener('click', decrementerClicked);
```

```html
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="utf-8">
	<link rel="stylesheet" href="./index.css">
	<title>Learn ReactJS</title>
</head>

<body>
  <main id="app">
    <p id='counter'>Waiting for current state.</p>
    <button id='incrementer'>+</button>
    <button id='decrementer'>-</button>
  </main>
	
</body>
<!-- Do Not Remove -->
<script src="https://content.codecademy.com/courses/React/react-16-redux-4-bundle.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/redux/4.0.5/redux.min.js" integrity="sha512-P36ourTueX/PrXrD4Auc1kVLoTE7bkWrIrkaM0IG2X3Fd90LFgTRogpZzNBssay0XOXhrIgudf4wFeftdsPDiQ==" crossorigin="anonymous"></script>
<script src="./store.js"></script>
</html>
```

```css
body {
  margin: 0;
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', 'Roboto', 'Oxygen',
    'Ubuntu', 'Cantarell', 'Fira Sans', 'Droid Sans', 'Helvetica Neue',
    sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

code {
  font-family: source-code-pro, Menlo, Monaco, Consolas, 'Courier New',
    monospace;
}

#app {
  text-align: center;
  font-size: 40px;
}

button {
  height: 40px;
  width: 40px;
  font-size: 24px;
}

#counter {
  margin-bottom: 5px;
}
```