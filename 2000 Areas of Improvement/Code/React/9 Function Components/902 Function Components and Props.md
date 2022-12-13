---
created: Tuesday, December 13th 2022 - 07.24
updated: Tuesday, December 13th 2022 - 07.24
---
Function Components and Props

Like any component, function components can receive information via `props`.

To access these `props`, give your function component a parameter named `props`. Within the function body, you can access the props using this pattern: `props.propertyName`. You don’t need to use the `this` keyword.

```JSX
export function YesNoQuestion (props) {
  return (
    <div>
      <p>{props.prompt}</p>
      <input value="Yes" />
      <input value="No" />
    </div>
  );
}
 
ReactDOM.render(
  <YesNoQuestion prompt="Have you eaten an apple today?" />,
  document.getElementById('app');
);
```

In the above example, we pass a value of “Have you eaten an apple today?” as the `prompt` prop when rendering `YesNoQuestion`.

---

```JSX
// NewFriend.js

import React from 'react';
import ReactDOM from 'react-dom';

export function NewFriend (props) {
		return (
      <div>
        <img src={props.src} />
      </div>
    );
}

ReactDOM.render(
  <NewFriend src="https://content.codecademy.com/courses/React/react_photo-squid.jpg" />,
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