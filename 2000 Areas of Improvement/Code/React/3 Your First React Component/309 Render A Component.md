---
created: Monday, December 12th 2022 - 06.23
updated: Monday, December 12th 2022 - 06.23
---
You have learned that a component class needs a set of instructions, which tell the component class how to build components. When you make a new component class, these instructions are the body of your class declaration:

```JSX
class MyComponentClass extends React.Component
{ // everything in between these curly-braces is instructions for how to build components
 
  render() {
    return <h1>Hello world</h1>;
  }
}
```

This class declaration results in a new component class, in this case named `MyComponentClass`. `MyComponentClass` has one method, named `render`. This all happens via standard JavaScript class syntax.

You _haven’t_ learned how these instructions actually work to make components! When you make a component by using the expression `<MyComponentClass />`, what do these instructions do?

Whenever you make a component, that component _inherits_ all of the methods of its component class. `MyComponentClass` has one method: `MyComponentClass.render()`. Therefore, `<MyComponentClass />` also has a method named `render`.

You could make a million different `<MyComponentClass />` instances, and each one would inherit this same exact `render` method.

This lesson’s final exercise is to _render_ your component. In order to render a component, that component needs to have a method named `render`. Your component has this! It _inherited_ a method named `render` from `MyComponentClass`.

Since your component has a render method, all that’s left to do is call it. This happens in a slightly unusual way.

To call a component’s `render` method, you pass that component to `ReactDOM.render()`. Notice your component, being passed as `ReactDOM.render()`‘s first argument:

```JSX
ReactDOM.render(
  <MyComponentClass />,
  document.getElementById('app')
);
```

`ReactDOM.render()` will tell `<MyComponentClass />` to call _its_ render method.

`<MyComponentClass />` will call its render method, which will return the JSX element `<h1>Hello world</h1>`. `ReactDOM.render()` will then take that resulting JSX element, and add it to the virtual DOM. This will make “Hello world” appear on the screen.

---

```JSX
import React from 'react';
import ReactDOM from 'react-dom';

class MyComponentClass extends React.Component {
  render() {
    return <h1>Hello world</h1>;
  }
}

// component goes here:
<MyComponentClass />

ReactDOM.render(<MyComponentClass />, document.getElementById('app'));
```