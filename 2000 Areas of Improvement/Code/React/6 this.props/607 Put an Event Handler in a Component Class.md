---
created: Monday, December 12th 2022 - 21.09
updated: Monday, December 12th 2022 - 21.09
---
Put an Event Handler in a Component Class

You can, and often will, pass functions as `props`. It is especially common to pass _event handler_ functions.

In the next lesson, you will pass an event handler function as a prop. However, you have to _define_ an event handler before you can pass one anywhere. In this lesson, you will define an event handler function.

How do you define an event handler in React?

You define an event handler as a method on the component class, just like the _render_ method.

Take a look in the code editor. On lines 4 through 8, an _event handler_ method is defined, with similar syntax as the render method. On line 12, that event handler method is attached to an _event_ (a click event, in this case).

---

```JSX
// Example.js

import React from 'react';

class Example extends React.Component {
  handleEvent() {
    alert(`I am an event handler.
      If you see this message,
      then I have been called.`);
  }

  render() {
    return (
      <h1 onClick={this.handleEvent}>
        Hello world
      </h1>
    );
  }
}
```

```JSX
// Talker.js

import React from 'react';
import ReactDOM from 'react-dom';
import { Button } from './Button';


class Talker extends React.Component {
  talk () {
    let speech = '';
    for (let i = 0; i < 10000; i++) {
      speech += 'blah ';
    }
    alert(speech);
  }
  
  render() {
    return <Button />;
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
      <button>
        Click me!
      </button>
    );
  }
}
```