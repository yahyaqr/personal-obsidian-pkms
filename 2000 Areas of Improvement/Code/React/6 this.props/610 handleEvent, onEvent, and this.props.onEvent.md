---
created: Monday, December 12th 2022 - 21.12
updated: Monday, December 12th 2022 - 21.12
---
handleEvent, onEvent, and this.props.onEvent

Let’s talk about naming things.

When you pass an _event handler_ as a prop, as you just did, there are two names that you have to choose.

Both naming choices occur in the _parent_ component class - that is, in the component class that defines the event handler and passes it.

The first name that you have to choose is the name of the event handler itself.

Look at **Talker.js**, lines 6 through 12. This is our event handler. We chose to name it `talk`.

The second name that you have to choose is the name of the prop that you will use to _pass_ the event handler. This is the same thing as your attribute name.

For our prop name, we also chose `talk`, as shown on line 15:

```JSX
return <Button talk={this.talk} />;
```

These two names can be whatever you want. However, there is a naming convention that they often follow. You don’t have to follow this convention, but you should understand it when you see it.

Here’s how the naming convention works: first, think about what _type of event_ you are listening for. In our example, the event type was “click.”

If you are listening for a “click” event, then you name your _event handler_ `handleClick`. If you are listening for a “keyPress” event, then you name your event handler `handleKeyPress`:

```JSX
class MyClass extends React.Component {
  handleHover() {
    alert('I am an event handler.');
    alert('I will be called in response to "hover" events.');
  }
}
```

Your prop name should be the word `on`, plus your event type. If you are listening for a “click” event, then you name your prop `onClick`. If you are listening for a “keyPress” event, then you name your prop `onKeyPress`:

```JSX
class MyClass extends React.Component {
  handleHover() {
    alert('I am an event handler.');
    alert('I will listen for a "hover" event.');
  }
 
  render() {
    return <Child onHover={this.handleHover} />;
  }
}
```

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