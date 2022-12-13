---
created: Monday, December 12th 2022 - 21.15
updated: Monday, December 12th 2022 - 21.15
---
defaultProps

Take a look at the `Button` component class.

Notice that on line 8, `Button` expects to receive a prop named `text`. The received `text` will be displayed inside of a `<button></button>` element.

What if nobody passes any `text` to `Button`?

If nobody passes any `text` to `Button`, then `Button`‘s display will be blank. It would be better if `Button` could display a default message instead.

You can make this happen by giving your component class a property named `defaultProps`:

```JSX
class Example extends React.Component {
  render() {
    return <h1>{this.props.text}</h1>;
  }
}
 
Example.defaultProps;
```

The `defaultProps` property should be equal to an object:

```JSX
class Example extends React.Component {
  render() {
    return <h1>{this.props.text}</h1>;
  }
}
 
// Set defaultProps equal to an object:
Example.defaultProps = {};
```

Inside of this object, write properties for any default `props` that you’d like to set:

```JSX
class Example extends React.Component {
  render() {
    return <h1>{this.props.text}</h1>;
  }
}
 
Example.defaultProps = { text: 'yo' };  
```

If an `<Example />` doesn’t get passed any text, then it will display “yo.”

If an `<Example />` _does_ get passed some text, then it will display that passed-in text.

---

```JSX
// Button.js

import React from 'react';
import ReactDOM from 'react-dom';

class Button extends React.Component {
  render() {
    return (
      <button>
        {this.props.text}
      </button>
    );
  }
}

// defaultProps goes here:
Button.defaultProps = { text: 'I am a button' };

ReactDOM.render(
  <Button text="" />, 
  document.getElementById('app')
);
```