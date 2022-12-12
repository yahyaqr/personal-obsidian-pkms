Create a Component Class

You’ve learned that a _React component_ is a small, reusable chunk of code that is responsible for one job, which often involves rendering HTML.

Here’s another fact about components: we can use a JavaScript class to define a new React component. We can also define components with JavaScript functions, but we’ll focus on _class components_ first.

All class components will have some methods and properties in common (more on this later). Rather than rewriting those same properties over and over again every time, we extend the `Component` class from the React library. This way, we can use code that we import from the React library, without having to write it over and over again ourselves.

After we _define_ our class component, we can use it to _render_ as many instances of that component as we want.

What _is_ `React.Component`, and how do you use it to make a component class?

`React.Component` is a JavaScript _class_. To create your own component class, you must _subclass_ `React.Component`. You can do this by using the syntax `class YourComponentNameGoesHere extends React.Component {}`.

JavaScript classes and subclassing are a complex topic beyond the scope of this course. If you aren’t comfortable with them, here are some good resources to consult: [1](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes) [2](https://hacks.mozilla.org/2015/07/es6-in-depth-classes/) [3](https://hacks.mozilla.org/2015/08/es6-in-depth-subclassing/) [4](http://exploringjs.com/es6/ch_classes.html).

Take another look at the code from the first exercise:

```JSX
import React from 'react';
import ReactDOM from 'react-dom';
 
class MyComponentClass extends React.Component {
  render() {
    return <h1>Hello world</h1>;
  }
}
 
ReactDOM.render(
    <MyComponentClass />, 
    document.getElementById('app')
);
```

A lot of it is still unfamiliar, but you can understand more than you could before!

On line 4, you know that you are declaring a new _component class_, which is like a factory for building React components. You know that `React.Component` is a class, which you must subclass in order to create a component class of your own. You also know that `React.Component` is a property on the object which was returned by `import React from 'react'` on line 1.

---

```JSX
import React from 'react';
import ReactDOM from 'react-dom';

class MyComponentClass extends React.Component {
  render()
  {
    return <h1>Hello world</h1>
  }
};
```