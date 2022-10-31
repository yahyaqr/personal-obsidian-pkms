---
created: Sunday, October 30th 2022 - 23.40
updated: Sunday, October 30th 2022 - 23.40
---
```js
import React from 'react';
import ReactDOM from 'react-dom';
import { createStore } from 'redux';

// REDUX CODE
///////////////////////////////////

const increment = () => {
  return {type: 'increment'} 
}

const decrement = () => { 
  return {type: 'decrement'}
}

const initialState = 0;
const counterReducer = (state = initialState, action) => {
  switch (action.type) {
    case 'increment':
      return state + 1;
    case 'decrement':
      return state - 1;
    default:
      return state; 
  }
} 

const store = createStore(counterReducer);

// REACT CODE
///////////////////////////////////

const render = () => {
  ReactDOM.render(
    <CounterApp 
      state={store.getState()}
    />,
    document.getElementById('root')
  )
}
render();

// Render once with the initial state.
// Subscribe render to changes to the store's state.
function CounterApp(props) {
  const state = props.state;
  
  const onIncrementButtonClicked = () => {
    // Dispatch an 'increment' action.
    store.dispatch(increment());
  }
 
  const onDecrementButtonClicked = () => {
    // Dispatch an 'decrement' action.
    store.dispatch(decrement());
  }
  
  return (   
    <div id='counter-app'>
      <h1> {state} </h1>
      <button onClick={onIncrementButtonClicked}>+</button> 
      <button onClick={onDecrementButtonClicked}>-</button>
    </div>
  )
}
store.subscribe(render);
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
  <div id="root">
  </div>
</body>
<!-- Do Not Remove -->
<script src="https://content.codecademy.com/courses/React/react-16-redux-4-bundle.min.js"></script>
<script src="./store.compiled.js"></script>
</html>
```

```css
#root {
  text-align: center;
  font-size: 25px;
}

button {
  height: 40px;
  width: 40px;
  font-size: 24px;
}

p {
  margin-bottom: 5px;
}
```