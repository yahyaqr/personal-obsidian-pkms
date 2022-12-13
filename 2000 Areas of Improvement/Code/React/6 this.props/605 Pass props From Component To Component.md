---
created: Monday, December 12th 2022 - 21.06
updated: Monday, December 12th 2022 - 21.06
---
Pass props From Component To Component

You have learned how to pass a `prop` to a component:

```JSX
<Greeting firstName="Esmerelda" />
```

You have also learned how to access and display a passed-in `prop`:

```JSX
render() {  return <h1>{this.props.firstName}</h1>;}
```

The most common use of `props` is to pass information to a component, _from a different component_. You haven’t done that yet, but it’s very similar to what you’ve seen already.

In this exercise, you will pass a `prop` from one component to another.

**A curmudgeonly clarification about grammar:**  
You may have noticed some loose usage of the words prop and `props`. Unfortunately, this is pretty inevitable.

`props` is the name of the object that stores passed-in information. `this.props` refers to that storage object. At the same time, each piece of passed-in information is called a prop. This means that `props` could refer to two pieces of passed-in information, or it could refer to the object that stores those pieces of information :(

---

```JSX
// Greeting.js

import React from 'react';

export class Greeting extends React.Component {
  render() {
    return <h1>Hi there, {this.props.name}!</h1>;
  }
}
```

```JSX
// App.js

import React from 'react';
import ReactDOM from 'react-dom';
import { Greeting } from './Greeting';

class App extends React.Component {
  render() {
    return (
      <div>
        <h1>
          Hullo and, "Welcome to The Newzz," "On Line!"
        </h1>
        <Greeting name="Andrea" />
        <article>
          Latest newzz:  where is my phone?
        </article>
      </div>
    );
  }
}

ReactDOM.render(
  <App />, 
  document.getElementById('app')
);
```