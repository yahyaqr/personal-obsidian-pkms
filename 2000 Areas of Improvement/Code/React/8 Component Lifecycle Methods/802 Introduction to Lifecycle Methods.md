---
created: Tuesday, December 13th 2022 - 07.19
updated: Tuesday, December 13th 2022 - 07.19
---
Introduction to Lifecycle Methods

React components have several methods, called _lifecycle methods_, that are called at different parts of a component’s lifecycle. This is how you, the programmer, deal with the lifecycle of a component.

You may not have known it, but you’ve already used two of the most common lifecycle methods: `constructor()` and `render()`! `constructor()` is the first method called during the mounting phase. `render()` is called later during the mounting phase, to render the component for the first time, and during the updating phase, to re-render the component.

Notice that lifecycle methods don’t necessarily correspond one-to-one with part of the lifecycle. `constructor()` only executes during the mounting phase, but `render()` executes during both the mounting and updating phase.

With this new understanding, let’s build a simple clock component.

---

```JSX
// Clock.js

import React from 'react';
import ReactDOM from 'react-dom';

class Clock extends React.Component {
  // Add your methods in here.
  constructor(props) {
    super(props);
    this.state = { date: new Date() };
  }

  render() {
    return (
      <div>
        { this.state.date.toLocaleTimeString()}
      </div>
    );
  }
}

ReactDOM.render(<Clock />, document.getElementById('app'));
```