---
created: Tuesday, December 13th 2022 - 07.31
updated: Tuesday, December 13th 2022 - 07.31
---
Use State Setter Outside of JSX

Let’s see how to manage the changing value of a string as a user types into a text input field:

```JSX
import React, { useState } from 'react';
 
export default function EmailTextInput() {
  const [email, setEmail] = useState('');
  const handleChange = (event) => {
    const updatedEmail = event.target.value;
    setEmail(updatedEmail);
  }
 
  return (
    <input value={email} onChange={handleChange} />
  );
}
```

Let’s break down how this code works!

-   The square brackets on the left side of the assignment operator signal [array destructuring](https://www.codecademy.com/content-items/92a5f93c6dbc6794d83e00383fc3af68)
-   The local variable named `email` is assigned the current state value at index `0` from the array returned by `useState()`
-   The local variable named `setEmail()` is assigned a reference to the state setter function at index `1` from the array returned by `useState()`
-   It’s convention to name this variable using the current state variable (`email`) with “set” prepended

The JSX input tag has an event listener called `onChange`. This event listener calls an _event handler_ each time the user types something in this element. In the example above, our event handler is defined inside of the definition for our function component, but outside of our JSX. Earlier in this lesson, we wrote our event handlers right in our JSX. Those inline event handlers work perfectly fine, but when we want to do something more interesting than just calling the state setter with a static value, it’s a good idea to separate that logic from everything else going on in our JSX. This separation of concerns makes our code easier to read, test, and modify.

This is so common in React code, that we can comfortably simplify this:

```JSX
const handleChange = (event) => {
  const newEmail = event.target.value;
  setEmail(newEmail);
}
```

To this:

```JSX
const handleChange = (event) => setEmail(event.target.value);
```

Or even, use [object destructuring](https://www.codecademy.com/content-items/92a5f93c6dbc6794d83e00383fc3af68?) to just write this:

```JSX
const handleChange = ({target}) => setEmail(target.value);
```

All three of these code snippets behave the same way, so there really isn’t a right and wrong between these different ways of doing this. We’ll use the last, most concise version moving forward.

---

```JSX
// PhoneNumber.js

import React, { useState } from 'react';

// regex to match numbers between 1 and 10 digits long
const validPhoneNumber = /^\d{1,10}$/;

export default function PhoneNumber() {
  // declare current state and state setter 
  const [phone, setPhone] = useState('');

  const handleChange = ({ target })=> {
    const newPhone = target.value;
    const isValid = validPhoneNumber.test(newPhone);
    if (isValid) {
        // update state 
        setPhone(newPhone);
    }
    // just ignore the event, when new value is invalid
  };

  return (
    <div className='phone'>
      <label for='phone-input'>Phone: </label>
      <input id='phone-input' value={phone} onChange={handleChange} />
    </div>
  );
}
```