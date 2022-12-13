---
created: Tuesday, December 13th 2022 - 07.34
updated: Tuesday, December 13th 2022 - 07.34
---
Objects in State

When we work with a set of related variables, it can be very helpful to group them in an object. Let’s look at an example!

```JSX
export default function Login() {
  const [formState, setFormState] = useState({});
 
  const handleChange = ({ target }) => {
    const { name, value } = target;
    setFormState((prev) => ({
      ...prev,
      [name]: value
    }));
  };
 
  return (
    <form>
      <input
        value={formState.firstName}
        onChange={handleChange}
        name="firstName"
        type="text"
      />
      <input
        value={formState.password}
        onChange={handleChange}
        type="password"
        name="password"
      />
    </form>
  );
}
```

A few things to notice:

-   We use a state setter callback function to update state based on the previous value
-   The spread syntax is the same for objects as for arrays: `{ ...oldObject, newKey: newValue }`
-   We reuse our event handler across multiple inputs by using the input tag’s `name` attribute to identify which input the change event came from

Once again, when updating the state with `setFormState()` inside a function component, we do not modify the same object. We must copy over the values from the previous object when setting the next value of state. Thankfully, the spread syntax makes this super easy to do!

Anytime one of the input values is updated, the `handleChange()` function will be called. Inside of this event handler, we use object destructuring to unpack the `target` property from our `event` object, then we use object destructuring again to unpack the `name` and `value` properties from the `target` object.

Inside of our state setter callback function, we wrap our curly brackets in parentheses like so: `setFormState((prev) => ({ ...prev }))`. This tells JavaScript that our curly brackets refer to a new object to be returned. We use `...`, the spread operator, to fill in the corresponding fields from our previous state. Finally, we overwrite the appropriate key with its updated value. Did you notice the square brackets around the `name`? This [Computed Property Name](http://eloquentcode.com/computed-property-names-in-javascript) allows us to use the string value stored by the `name` variable as a property key!

---

```JSX
// EditProfile.js

import React, { useState } from "react";

export default function EditProfile() {
  const [profile, setProfile] = useState({});

  const handleChange = ({ target }) => {
    const {name, value} = target;
    setProfile((prevProfile) => ({
      ...prevProfile,
      [name]: value
    }));
  };

  const handleSubmit = (event) => {
    event.preventDefault();
    alert(JSON.stringify(profile, '', 2));
  };

  return (
    <form onSubmit={handleSubmit}>
      <input
        value={profile.firstName || ''}
        name="firstName"
        type="text"
        placeholder="First Name"
        onChange={handleChange}
      />
      <input
        value={profile.lastName || ''}
        type="text"
        name="lastName"
        placeholder="Last Name"
        onChange={handleChange}
      />
      <input
        value={profile.bday || ''}
        type="date"
        name="bday"
        onChange={handleChange}
      />
      <input
        value={profile.password || ''}
        type="password"
        name="password"
        placeholder="Password"
        onChange={handleChange}
      />
      <button type="submit">Submit</button>
    </form>
    
  );
}
```