---
created: Monday, December 12th 2022 - 06.19
updated: Monday, December 12th 2022 - 06.19
---
Name a Component Class

Good! Subclassing `React.Component` is the way to declare a new _component class_.

When you declare a new component class, you need to give that component class a _name._ On our finished component, our component class’s name was `MyComponentClass`:

```JSX
class MyComponentClass extends React.Component {
  render() {
    return <h1>Hello world</h1>;
  }
}
```

Component class variable names must begin with capital letters!

This adheres to JavaScript’s class syntax. This naming convention is also seen in other languages that write [class names in UpperCamelCase, like Java](https://en.wikipedia.org/wiki/Naming_convention_(programming)#Java).

In addition, there is a React-specific reason why component class names must always be capitalized. We’ll get to that soon!

---

```JSX
import React from 'react';
import ReactDOM from 'react-dom';

class MyComponentClass extends React.Component {
  render()
  {
    return <h1>Hello world</h1>
  }
};
```