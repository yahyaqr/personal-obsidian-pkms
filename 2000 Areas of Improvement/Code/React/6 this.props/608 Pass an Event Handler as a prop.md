---
created: Monday, December 12th 2022 - 21.10
updated: Monday, December 12th 2022 - 21.10
---
Pass an Event Handler as a prop

Good! You’ve defined a new method on the `Talker` component class. Now you’re ready to _pass_ that function to another component.

You can pass a method in the exact same way that you pass any other information. Behold, the mighty JavaScript.

---

```JSX
// Talker.js

import React from 'react';
import ReactDOM from 'react-dom';
import { Button } from './Button';

class Talker extends React.Component {
  handleClick() {
    let speech = '';
    for (let i = 0; i < 10000; i++) {
      speech += 'blah ';
    }
    alert(speech);
  }
  
  render() {
    return <Button onClick={this.handleClick} />;
  }
}

ReactDOM.render(
  <Talker />,
  document.getElementById('app')
);
```

```JSX
// Button.js

import React from 'react';

export class Button extends React.Component {
  render() {
    return (
      <button onClick={this.props.onClick} >
        Click me!
      </button>
    );
  }
}
```