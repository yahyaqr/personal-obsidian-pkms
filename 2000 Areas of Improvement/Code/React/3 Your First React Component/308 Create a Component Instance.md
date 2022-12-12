---
created: Monday, December 12th 2022 - 06.21
updated: Monday, December 12th 2022 - 06.21
---
Create a Component Instance

`MyComponentClass` is now a working _component class!_ It’s ready to follow its instructions and make some React components.

So, let’s make a React component! It only takes one more line:

```JSX
<MyComponentClass />
```

To make a React component, you write a _JSX element._ Instead of naming your JSX element something like `h1` or `div` like you’ve done before, give it the same name as a _component class_. Voilà, there’s your _component instance!_

JSX elements can be either HTML-like, or _component instances_. JSX uses capitalization to distinguish between the two! _That_ is the React-specific reason why component class names must begin with capital letters. In a JSX element, that capitalized first letter says, “I will be a component instance and not an HTML tag.”

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