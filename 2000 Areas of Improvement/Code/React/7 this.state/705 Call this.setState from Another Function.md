Call this.setState from Another Function

The most common way to call `this.setState()` is to call a custom function that _wraps_ a `this.setState()` call. `.makeSomeFog()` is an example:

```JSX
class Example extends React.Component {
  constructor(props) {
    super(props);
    this.state = { weather: 'sunny' };
    this.makeSomeFog = this.makeSomeFog.bind(this);
  }
 
  makeSomeFog() {
    this.setState({
      weather: 'foggy'
    });
  }
}
```

Notice how the method `makeSomeFog()` contains a call to `this.setState()`.

You may have noticed a weird line in there:

```JSX
this.makeSomeFog = this.makeSomeFog.bind(this);
```

This line is necessary because `makeSomeFog()`‘s body contains the word `this`. We’ll talk about it more soon!

Let’s walk through how a function wrapping `this.setState()` might work in practice. In the code editor, read **Mood.js** all the way through.

Here is how a `<Mood />`‘s state would be set:

1.  A user triggers an _event_ (in this case a click event, triggered by clicking on a `<button></button>`).
    
2.  The event from Step 1 is being listened for (in this case by the `onClick` attribute on line 20).
    
3.  When this listened-for event occurs, it calls an _event handler_ function (in this case, `this.toggleMood()`, called on line 20 and defined on lines 11-14).
    
4.  Inside of the body of the _event handler_, `this.setState()` is called (in this case on line 13).
    
5.  The component’s `state` is changed!
    

Due to the way that event handlers are bound in JavaScript, `this.toggleMood()` loses its `this` when it is used on line 20. Therefore, the expressions `this.state.mood` and `this.setState` on lines 12 and 13 won’t mean what they’re supposed to… _unless_ you have already bound the correct `this` to `this.toggleMood`.

That is why we must bind `this.toggleMood` to `this` on line 8.

For an in-depth explanation of this kind of binding trickery, begin with [the React docs](https://facebook.github.io/react/docs/handling-events.html). For the less curious, just know that in React, whenever you define an event handler that uses `this`, you need to add `this.methodName = this.methodName.bind(this)` to your constructor function.

Look at the statement on line 12. What does that do?

Line 12 declares a `const` named `newMood` equal to the opposite of `this.state.mood`. If `this.state.mood` is “good”, then `newMood` will be “bad,” and vice versa.

A `<Mood />` instance would display “I’m feeling good!” along with a button. Clicking on the button would change the display to “I’m feeling bad!” Clicking again would change back to “I’m feeling good!”, etc. Try to follow the step-by-step walkthrough in **Mood.js** and see how all of this works.

One final note: you _can’t_ call `this.setState()` from inside of the render function! We’ll explain why in the next exercise.

---

```JSX
import React from 'react';
import ReactDOM from 'react-dom';

class Mood extends React.Component {
  constructor(props) {
    super(props);
    this.state = { mood: 'good' };
    this.toggleMood = this.toggleMood.bind(this);
  }

  toggleMood() {
    const newMood = this.state.mood == 'good' ? 'bad' : 'good';
    this.setState({ mood: newMood });
  }

  render() {
    return (
      <div>
        <h1>I'm feeling {this.state.mood}!</h1>
        <button onClick={this.toggleMood}>
          Click Me
        </button>
      </div>
    );
  }
}

ReactDOM.render(<Mood />, document.getElementById('app'));
```