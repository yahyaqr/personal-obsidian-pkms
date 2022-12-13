---
created: Tuesday, December 13th 2022 - 07.21
updated: Tuesday, December 13th 2022 - 07.21
---
componentDidUpdate

Remember the three parts of a component’s lifecycle:

1.  _Mounting_, when the component is being initialized and put into the DOM for the first time
2.  _Updating_, when the component updates as a result of changed state or changed props
3.  _Unmounting_, when the component is being removed from the DOM

We’ve looked at mounting (`constructor()`, `render()`, and `componentDidMount()`). We’ve looked at unmounting (`componentWillUnmount()`). Let’s finish by looking at the updating phase.

An update is caused by changes to props or state. You’ve already seen this happen a bunch of times. Every time you’ve called `setState()` with new data, you’ve triggered an update. Every time you change the props passed to a component, you’ve caused it to update.

When a component updates, it calls [several methods](https://reactjs.org/docs/react-component.html#updating), but only two are commonly used.

The first is `render()`, which we’ve seen in every React component. When a component’s props or state changes, `render()` is called.

The second, which we haven’t seen yet, is `componentDidUpdate()`. Just like `componentDidMount()` is a good place for mount-phase setup, `componentDidUpdate()` is a good place for update-phase work.

---

```JSX
// Clock.js

import React from "react";

export class Clock extends React.Component {
  constructor(props) {
    super(props);
    this.state = { date: new Date() };
  }
  startInterval() {
    clearInterval(this.intervalID);
    let delay = this.props.isPrecise ? 100 : 1000;
    this.intervalID = setInterval(() => {
      this.setState({ date: new Date() });
    }, delay);
  }

  render() {
    return (
      <div>
        {this.props.isPrecise
          ? this.state.date.toISOString()
          : this.state.date.toLocaleTimeString()}
      </div>
    );
  }
  componentDidMount() {
    this.startInterval();
  }
  componentDidUpdate(prevProps) {
    if (this.props.isPrecise === prevProps.isPrecise) {
      return;
    }
    clearInterval(this.intervalID);
    this.startInterval();
  }
  componentWillUnmount() {
    clearInterval(this.intervalID);
  }
}

```