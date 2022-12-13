---
created: Tuesday, December 13th 2022 - 07.17
updated: Tuesday, December 13th 2022 - 07.17
---
Review

We’ve come to the end of the lesson. We’ve learned about the three major phases of a component’s lifecycle:

1.  _Mounting_, when the component is being initialized and put into the DOM for the first time. We saw that the `constructor`, `render()`, and `componentDidMount()` are called during this phase.
2.  _Updating_, when the component updates as a result of changed state or changed props. We saw that `render()` and `componentDidUpdate()` are called during this phase.
3.  _Unmounting_, when the component is being removed from the DOM. We saw that `componentWillUnmount()` was called here, which was a good time to clean things up.

We also learned about setting up side-effects and tearing them down. We now know how to make more robust, complex components!

To your right is a reference that you can use. It shows the three phases of a component’s lifecycle and which methods are called at each phase. You can also refer to [this interactive diagram](https://projects.wojtekmaj.pl/react-lifecycle-methods-diagram/).

For more, you can read React’s official documentation. See [“State and Lifecycle”](https://reactjs.org/docs/state-and-lifecycle.html) and [the docs for `React.Component`](https://reactjs.org/docs/react-component.html).

---

https://projects.wojtekmaj.pl/react-lifecycle-methods-diagram/