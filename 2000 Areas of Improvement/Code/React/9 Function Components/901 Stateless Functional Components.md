---
created: Tuesday, December 13th 2022 - 07.23
updated: Tuesday, December 13th 2022 - 07.23
---
Stateless Functional Components

In the code editor, take a look at **Example.js**. The first `Example` component is defined as a JavaScript class, but it doesn’t have to be! In React, we can also define components as JavaScript functions — we call them _function components_ to differentiate them from _class components_.

In the latest versions of React, function components can do everything that class components can do. In most cases, however, function components offer a more elegant, concise way of creating React components. This lesson will focus on converting a class component to a function component and adding props, which are available in all versions of React.

Compare the `Example` class component and the `Example` function component. For the most basic function components, all you need to do is remove the beginning `render() {` and ending `}` of the `render()` method:

```JSX
render() { // Delete this
  return <h1>Hello</h1>
} // Delete this
```

To put it in other words: the function component should return the same JSX that was originally returned by the `render()` method.

---

```JSX
// Friend.js

import React from 'react';
import ReactDOM from 'react-dom';

export const Friend = () => {
    return <img src="https://content.codecademy.com/courses/React/react_photo-octopus.jpg" />;
};

ReactDOM.render(
	<Friend />,
	document.getElementById('app')
);
```

```JSX
// Example.js

// A component class written in the usual way:
export class MyComponentClass extends React.Component {
  render() {
    return <h1>Hello world</h1>;
  }
}

// The same component class, written as a stateless functional component:
export const MyComponentClass = () => {
  return <h1>Hello world</h1>;
}

// Works the same either way:
ReactDOM.render(
	<MyComponentClass />,
	document.getElementById('app')
);
```