---
created: Tuesday, December 13th 2022 - 07.32
updated: Tuesday, December 13th 2022 - 07.32
---
Set From Previous State

Often, the next value of our state is calculated using the current state. In this case, it is best practice to update state with a callback function. If we do not, we risk capturing outdated, or “stale”, state values.

Let’s take a look at the following code:

```JSX
import React, { useState } from 'react';
 
export default function Counter() {
  const [count, setCount] = useState(0);
 
  const increment = () => setCount(prevCount => prevCount + 1);
 
  return (
    <div>
      <p>Wow, you've clicked that button: {count} times</p>
      <button onClick={increment}>Click here!</button>
    </div>
  );
}
```

When the button is pressed, the `increment()` event handler is called. Inside of this function, we use our `setCount()` state setter in a new way! Because the next value of `count` depends on the previous value of `count`, we pass a callback function as the argument for `setCount()` instead of a value (as we’ve done in previous exercises).

```JSX
setCount(prevCount => prevCount + 1)
```

When our state setter calls the callback function, this _state setter callback function_ takes our previous `count` as an argument. The value returned by this state setter callback function is used as the next value of `count` (in this case `prevCount + 1`). Note: We can just call `setCount(count +1)` and it would work the same in this example… but for reasons that are out of scope for this lesson, it is safer to use the callback method. If you’d like to learn more about why the callback method is safer, [this section of the docs](https://reactjs.org/docs/react-component.html#setstate) is a great place to start.

---

```JSX
// QuizNavbar.js

import React, { useState } from 'react';

export default function QuizNavBar({ questions }) {
  const [questionIndex, setQuestionIndex] = useState(0);

  // define event handlers 
  const goBack = () => setQuestionIndex((prevQuestionIndex) => prevQuestionIndex -1);
  const goToNext = () => setQuestionIndex((prevQuestionIndex) => prevQuestionIndex + 1);

  // determine if on the first question or not 
  const onFirstQuestion = questionIndex === 0;
  const onLastQuestion = questionIndex === questions.length - 1;

  return (
    <nav>
      <span>Question #{questionIndex + 1}</span>
      <div>
        <button onClick={goBack} disabled={onFirstQuestion} >
          Go Back
        </button>
        <button onClick={goToNext} disabled={onLastQuestion} >
          Next Question
        </button>
      </div>
    </nav>
  );
}
```