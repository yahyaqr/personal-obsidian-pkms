---
created: Tuesday, December 13th 2022 - 07.12
updated: Tuesday, December 13th 2022 - 07.12
---
Setting Initial State

A React component can access dynamic information in two ways: `props` and `state`.

Unlike `props`, a component’s `state` is _not_ passed in from the outside. A component decides its own `state`.

To make a component have `state`, give the component a `state` property. This property should be declared inside of a constructor method, like this:

```JSX
class Example extends React.Component {
  constructor(props) {
    super(props);
    this.state = { mood: 'decent' };
  }
 
  render() {
    return <div></div>;
  }
}
 
<Example />
```

Whoa, a constructor method? `super(props)`? What’s going on here? Let’s look more closely at this potentially unfamiliar code:

```JSX
constructor(props) {
  super(props);
  this.state = { mood: 'decent' };
}
```

`this.state` should be equal to an object, like in the example above. This object represents the initial “state” of any component instance. We’ll explain that more soon!

How about the rest of the code? `constructor` and `super` are both features of ES6, not unique to React. There is nothing particularly React-y about their usage here. A full explanation of their functionality is outside of the scope of this course, but we’d recommend [familiarizing](https://hacks.mozilla.org/2015/07/es6-in-depth-classes/) [yourself](http://exploringjs.com/es6/ch_classes.html). It is important to note that React components _always_ have to call `super` in their constructors to be set up properly.

Look at the bottom of the highest code example in this column. `<Example />` has a `state`, and its `state` is equal to `{ mood: 'decent' }`.

---

```JSX
import React from 'react';
import ReactDOM from 'react-dom';

class App extends React.Component {
	// constructor method begins here:
  constructor (props) {
    super(props);
    this.state = { title: 'Best App'};
  }

  render() {
    return (
      <h1>
        {this.state.title}
      </h1>
    );
  }
}

ReactDOM.render(<App />, document.getElementById('app'));
```