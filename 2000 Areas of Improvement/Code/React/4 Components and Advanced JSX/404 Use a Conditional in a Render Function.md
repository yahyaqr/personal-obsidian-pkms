---
created: Monday, December 12th 2022 - 06.29
updated: Monday, December 12th 2022 - 06.29
---
Use a Conditional in a Render Function

How might you use a _conditional_ statement inside of a `render()` function?

Select **TodaysPlan.js** to see one way of doing it.

Notice that the `if` statement is located _inside_ of the render function, but _before_ the `return` statement. This is pretty much the only way that you will ever see an `if` statement used in a render function.

---

```JSX
// App.js

import React from 'react';
import ReactDOM from 'react-dom';

const fiftyFifty = Math.random() < 0.5;

// New component class starts here:
class TonightsPlan extends React.Component {
  render() {
    let action;
    if (fiftyFifty) {
      action = "out";
    } else {
      action = "to bed";
    }

    return <h1>Tonight I'm going {action} WOOO</h1>;
  }
}

ReactDOM.render(<TonightsPlan/>, document.getElementById('app'));

```

```JSX
// TodaysPlan.js

import React from 'react';
import ReactDOM from 'react-dom';

class TodaysPlan extends React.Component {
  render() {
    let task;
    if (!apocalypse) {
      task = 'learn React.js'
    } else {
      task = 'run around'
    }

    return <h1>Today I am going to {task}!</h1>;
  }
}

ReactDOM.render(
	<TodaysPlan />,
	document.getElementById('app')
);
```