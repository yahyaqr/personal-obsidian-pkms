Hello World, Part II... THE COMPONENT

React applications are made out of _components._

What’s a component?

A component is a small, reusable chunk of code that is responsible for one job. That job is often to render some HTML.

Take a look at the code below. This code will create and render a new React component:

```JSX
import React from 'react';
import ReactDOM from 'react-dom';
 
class MyComponentClass extends React.Component {
  render() {
    return <h1>Hello world</h1>;
  }
};
 
ReactDOM.render(
  <MyComponentClass />,
  document.getElementById('app')
);
```

A lot of that code is probably unfamiliar. However, you can recognize some JSX in there, as well as `ReactDOM.render()`.

We are going to unpack that code, one small piece at a time. By the end of this lesson, you’ll understand how to build a React component!

> **A note from the Curriculum Developers**: In this course, we teach both [class components and function components](https://reactjs.org/docs/components-and-props.html#function-and-class-components). We start with class components because they are still widely used in legacy code, are common in tutorials/documentation found online, and are required for a few specific use-cases. In the module on Hooks, we introduce function components which are the recommended way of creating React components. From that point on, we use function components throughout the remainder of our React content.

---

```JSX
class MyComponentClass extends React.Component {
  render() {
    return <h1>Hello world</h1>;
  }
};

ReactDOM.render(
  <MyComponentClass />,
  document.getElementById('app')
);
```