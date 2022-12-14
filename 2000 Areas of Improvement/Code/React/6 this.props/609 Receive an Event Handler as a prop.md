Receive an Event Handler as a prop

Great! You just passed a function from `<Talker />` to `<Button />`.

In the code editor, select **Button.js**. Notice that `Button` renders a `<button></button>` element.

If a user clicks on this `<button></button>` element, then you want your passed-in `talk` function to get called.

That means that you need to attach `talk` to the `<button></button>` as an _event handler_.

How do you do that? The same way that you attach any event handler to a JSX element: you give that JSX element a special _attribute_. The attribute’s _name_ should be something like `onClick` or `onHover`. The attribute’s _value_ should be the event handler that you want to attach.

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