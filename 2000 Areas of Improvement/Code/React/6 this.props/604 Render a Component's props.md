---
created: Monday, December 12th 2022 - 21.05
updated: Monday, December 12th 2022 - 21.05
---
Render a Component's props

You just _passed_ information to a component’s `props` object!

You will often want a component to _display_ the information that you pass.

Here’s how to make a component display passed-in information:

1 - Find the _component class_ that is going to receive that information.  
2 - Include `this.props.name-of-information` in that component class’s _render_ method’s `return` statement.

---

```JSX
import React from 'react';
import ReactDOM from 'react-dom';

class Greeting extends React.Component {
  render() {
    return <h1>Hi there, {this.props.firstName}</h1>;
  }
}

ReactDOM.render(
  <Greeting firstName='Andrea' />, 
  document.getElementById('app')
);
```