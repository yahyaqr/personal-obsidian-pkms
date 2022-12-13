---
created: Tuesday, December 13th 2022 - 07.30
updated: Tuesday, December 13th 2022 - 07.30
---
Initialize State

Great work building out your first stateful function component in the last exercise. Just like you used the State Hook to manage a variable with string values, we can use the State Hook to manage the value of any [primitive data type](https://www.codecademy.com/courses/introduction-to-javascript/lessons/introduction-to-javascript/exercises/types) and even data collections like arrays and objects!

Have a look at the following function component. What data type does this state variable hold?

```JSX
import React, { useState } from 'react';
 
function ToggleLoading() {
  const [isLoading, setIsLoading] = useState();
 
  return (
    <div>
      <p>The data is {isLoading ? 'Loading' : 'Not Loading'}</p>
      <button onClick={() => setIsLoading(true)}>
        Turn Loading On
      </button>
      <button onClick={() => setIsLoading(false)}>
        Turn Loading Off
      </button>
    </div>
  );
}
```

The `ToggleLoading()` function component above is using the simplest of all data types, a boolean. Booleans are frequently used in React applications to represent whether data has loaded or not. In the example above, we see that `true` and `false` values are passed to the state setter, `setIsLoading()`. This code works just fine as is, but what if we want our component to start off with `isLoading` set to `true`?

To initialize our state with any value we want, we simply pass the initial value as an argument to the `useState()` function call.

```JSX
const [isLoading, setIsLoading] = useState(true);
```

There are three ways in which this code affects our component:

1.  During the first render, the _initial state argument_ is used.
2.  When the state setter is called, React ignores the initial state argument and uses the new value.
3.  When the component re-renders for any other reason, React continues to use the same value from the previous render.

If we don’t pass an initial value when calling `useState()`, then the current value of the state during the first render will be `undefined`. Often, this is perfectly fine for the machines, but it can be unclear to the humans reading our code. So, we prefer to explicitly initialize our state. If we don’t have the value needed during the first render, we can explicitly pass `null` instead of just passively leaving the value as `undefined`.

---

```JSX
// ColorPicker.js

import React, { useState } from 'react';

const colorNames = ['Aquamarine', 'BlueViolet', 'Chartreuse', 'CornflowerBlue', 'Thistle', 'SpringGreen', 'SaddleBrown', 'PapayaWhip', 'MistyRose'];

export default function ColorPicker() {
  const [color, setColor] = useState('Tomato');

 const divStyle = {backgroundColor: color};

  return (
    <div style={divStyle}>
      <p>Selected color: {color}</p>
      {colorNames.map((colorName)=>(
        <button 
          onClick={() => setColor(colorName)} 
          key={colorName}>
       	     {colorName}
      	</button>
      ))}
    </div>
  );
}
```