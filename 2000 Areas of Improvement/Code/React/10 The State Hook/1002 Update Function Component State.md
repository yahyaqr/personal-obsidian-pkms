Update Function Component State

Let’s get started with the State Hook, the most common Hook used for building React components. The State Hook is a named export from the React library, so we import it like this:

```JSX
import React, { useState } from 'react';
```

`useState()` is a JavaScript function defined in the React library. When we call this function, it returns an array with two values:

-   _current state_ - the current value of this state
-   _state setter_ - a function that we can use to update the value of this state

Because React returns these two values in an array, we can assign them to local variables, naming them whatever we like. For example:

```JSX
const [toggle, setToggle] = useState();
```

Let’s have a look at an example of a function component using the State Hook:

```JSX
import React, { useState } from "react";
 
function Toggle() {
  const [toggle, setToggle] = useState();
 
  return (
    <div>
      <p>The toggle is {toggle}</p>
      <button onClick={() => setToggle("On")}>On</button>
      <button onClick={() => setToggle("Off")}>Off</button>
    </div>
  );
}
```

Notice how the state setter function, `setToggle()`, is called by our `onClick` _event listeners_. To update the value of `toggle` and re-render this component with the new value, all we need to do is call the `setToggle()` function with the next state value as an argument.

No need to worry about binding functions to class instances, working with constructors, or dealing with the `this` keyword. With the State Hook, updating state is as simple as calling a state setter function.

Calling the state setter signals to React that the component needs to re-render, so the whole function defining the component is called again. The magic of `useState()` is that it allows React to keep track of the current value of state from one render to the next!

---

```JSX
// ColorPicker.js

import React, { useState } from 'react';

export default function ColorPicker() {
  const [color, setColor] = useState();

 const divStyle = {backgroundColor: color};

  return (
    <div style={divStyle}>
      <p>The color is {color}</p>
      <button onClick={() => setColor('Aquamarine')}>
        Aquamarine
      </button>
      <button onClick={() => setColor('BlueViolet')}>
        BlueViolet
      </button>
      <button onClick={() => setColor('Chartreuse')}>
        Chartreuse
      </button>
      <button onClick={() => setColor('CornflowerBlue')}>
        CornflowerBlue
      </button>
    </div>
  );
}

```