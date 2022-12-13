---
created: Tuesday, December 13th 2022 - 07.14
updated: Tuesday, December 13th 2022 - 07.14
---
Update state with this.setState

A component can do more than just read its own state. A component can also _change_ its own state.

A component changes its state by calling the function `this.setState()`.

`this.setState()` takes two arguments: an _object_ that will update the component’s state, and a callback. You basically never need the callback.

In the code editor, take a look at **Example.js**. Notice that `<Example />` has a state of:

```JSX
{  mood:   'great',  hungry: false}
```

Now, let’s say that `<Example />` were to call:

```JSX
this.setState({ hungry: true });
```

After that call, here is what `<Example />`‘s state would be:

```JSX
{  mood:   'great',  hungry: true}
```

The `mood` part of the state remains unaffected!

`this.setState()` takes an object, and _merges_ that object with the component’s current state. If there are properties in the current state that aren’t part of that object, then those properties remain how they were.

---

```JSX
import React from 'react';

class Example extends React.Component {
  constructor(props) {
  	super(props);
    this.state = {
      mood:   'great',
      hungry: false
    };
  }

  render() {
    return <div></div>;
  }
}

<Example />
```