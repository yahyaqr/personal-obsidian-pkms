---
created: Tuesday, December 13th 2022 - 07.19
updated: Tuesday, December 13th 2022 - 07.19
---
componentDidMount

We’ve made a clock component, but it’s static. Wouldn’t it be nice if it updated?

At a high level, we’d like to update `this.state.date` with a new date once per second.

JavaScript has a helpful function, [`setInterval()`](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/setInterval), that will help us do just this. It lets us run a function on a set interval. In our case, we’ll make a function that updates `this.state.date`, and call it every second.

We’ll want to run some code that looks like this:

```JSX
// NOTE: This code doesn't clean itself up properly.
// We'll explore that in the next exercise.
const oneSecond = 1000;
setInterval(() => {
  this.setState({ date: new Date() });
}, oneSecond);
```

We have the code we want to run—that’s great. But where should we put this code? In other words, where in the component’s lifecycle should it go?

Remember, the component lifecycle has three high-level parts:

1.  _Mounting_, when the component is being initialized and put into the DOM for the first time
2.  _Updating_, when the component updates as a result of changed state or changed props
3.  _Unmounting_, when the component is being removed from the DOM

It’s certainly not in the unmounting phase—we don’t want to start our interval when the clock disappears from the screen! It’s also probably not useful during the updating phase—we want the interval to start as soon as the clock appears, and we don’t want to wait for an update. It probably makes sense to stick this code somewhere in the mounting phase.

We’ve seen two functions: the `render()` and the constructor. Can we put this code in either of those places?

-   `render()` isn’t a good candidate. For one, it executes during the mounting phase and the updating phase—too often for us. It’s also generally a bad idea to set up any kind of side-effect like this in `render()`, as it can create subtle bugs in the future.
-   `constructor()` is also not great. It does only execute during the mounting phase, so that’s good, but you should generally avoid side-effects like this in constructors because it violates something called the Single Responsibility Principle. In short, it’s not a constructor’s responsibility to start side-effects. ([You can read more about the principle on Wikipedia.](https://en.wikipedia.org/wiki/Single-responsibility_principle))

If it’s not `render()` or the constructor, then where? Enter a new lifecycle method, `componentDidMount()`.

`componentDidMount()` is the final method called during the mounting phase. The order is:

1.  The constructor
2.  `render()`
3.  `componentDidMount()`

In other words, it’s called after the component is rendered. This is where we’ll want to start our timer.

(Another method, [`getDerivedStateFromProps()`](https://reactjs.org/docs/react-component.html#static-getderivedstatefromprops), is called between the constructor and `render()`, but it is very rarely used and usually isn’t the best way to achieve your goals. We won’t be talking about it in this lesson.)

---

```JSX
// Clock.js

import React from 'react';
import ReactDOM from 'react-dom';

class Clock extends React.Component {
  constructor(props) {
    super(props);
    this.state = { date: new Date() };
  }
  
  render() {
    return <div>{this.state.date.toLocaleTimeString()}</div>;
  }

  componentDidMount() {
    // Paste your code here.
    const oneSecond = 1000;
    setInterval(() => {
      this.setState({ date: new Date() });
    }, oneSecond);
  }
}

ReactDOM.render(<Clock />, document.getElementById('app'));
```