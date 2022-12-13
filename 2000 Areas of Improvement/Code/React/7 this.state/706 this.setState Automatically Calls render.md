---
created: Tuesday, December 13th 2022 - 07.16
updated: Tuesday, December 13th 2022 - 07.16
---
this.setState Automatically Calls render

There’s something odd about all of this.

Look again at **Toggle.js**.

When a user clicks on the `<button></button>`, the `.changeColor()` method is called. Take a look at `.changeColor()`‘s definition.

`.changeColor()` calls `this.setState()`, which updates `this.state.color`. However, even if `this.state.color` is updated from `green` to `yellow`, that alone shouldn’t be enough to make the screen’s color change!

The screen’s color doesn’t change until `Toggle` _renders._

Inside of the render function, it’s this line:

```JSX
<div style={{background:this.state.color}}>
```

that changes a virtual DOM object’s color to the new `this.state.color`, eventually causing a change in the screen.

If you call `.changeColor()`, shouldn’t you then _also_ have to call `.render()` again? `.changeColor()` only makes it so that, the next time that you render, the color will be different. Why can you see the new background right away, if you haven’t re-rendered the component?

Here’s why: _Any time that you call this.setState(), this.setState() AUTOMATICALLY calls .render() as soon as the state has changed._

Think of `this.setState()` as actually being two things: `this.setState()`, immediately followed by `.render()`.

_That_ is why you can’t call `this.setState()` from inside of the `.render()` method! `this.setState()` _automatically_ calls `.render()`. If `.render()` calls `this.setState()`, then an infinite loop is created.

---

```JSX
import React from 'react';
import ReactDOM from 'react-dom';

const green = '#39D1B4';
const yellow = '#FFD712';

class Toggle extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      color: green
    }
    this.changeColor = this.changeColor.bind(this);
  }

  changeColor() {
    const toggleColor = this.state.color == green ? yellow : green;
    this.setState({ color: toggleColor });
  }

  render() {
    return (
      <div style={{background: this.state.color}}>
        <h1>
          Change my color
        </h1>
        <button onClick={this.changeColor}>
          Change color
        </button>
      </div>
    );
  }
}

ReactDOM.render(<Toggle />, document.getElementById('app'));
```