---
created: Tuesday, December 13th 2022 - 07.13
updated: Tuesday, December 13th 2022 - 07.13
---
Access a Component's state

To _read_ a component’s `state`, use the expression `this.state.name-of-property`:

```JSX
class TodayImFeeling extends React.Component {
  constructor(props) {
    super(props);
    this.state = { mood: 'decent' };
  }
 
  render() {
    return (
      <h1>
        I'm feeling {this.state.mood}!
      </h1>
    );
  }
}
```

The above component class reads a property in its `state` from inside of its `render` function.

Just like `this.props`, you can use `this.state` from any property defined inside of a component class’s body.

---

```JSX
import React from 'react';
import ReactDOM from 'react-dom';

class App extends React.Component {
	// constructor method begins here:
  constructor (props) {
    super(props);
    this.state = { title: 'Best App'};
  }

  render() {
    return (
      <h1>
        {this.state.title}
      </h1>
    );
  }
}

ReactDOM.render(<App />, document.getElementById('app'));
```