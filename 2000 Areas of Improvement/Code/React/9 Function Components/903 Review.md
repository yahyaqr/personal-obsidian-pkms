---
created: Tuesday, December 13th 2022 - 07.25
updated: Tuesday, December 13th 2022 - 07.25
---
Review

Well done! You’ve written your first function component. Here’s a recap:

-   _Function components_ are React components defined as JavaScript functions
-   Function components must return JSX
-   Function components may accept a `props` parameter. Expect it to be a JavaScript object

Although function components and class components can do the same things, you’ll see a lot of function components in the React documentation and example apps. Some developers prefer them over class components for their simplicity and straightforward features, like Hooks, which you’ll learn later in your coding journey.

---

```JSX
// Friend.js

import React from 'react';
import ReactDOM from 'react-dom';

// <Friend /> as function component
export const Friend = () => {
  return <img src='https://content.codecademy.com/courses/React/react_photo-octopus.jpg' />;
}

// <Friend /> as class component
// export class Friend extends React.Component {
// 	render() {
// 		return <img src='https://content.codecademy.com/courses/React/react_photo-octopus.jpg' />;
// 	}
// }

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