---
created: Monday, December 12th 2022 - 06.33
updated: Monday, December 12th 2022 - 06.33
---
A Component in a Render Function

Here is a `.render()` method that returns an HTML-like JSX element:

```JSX
class Example extends React.Component {
  render() {
    return <h1>Hello world</h1>;
  }
}
```

You’ve seen render methods return `<div></div>`s, `<p></p>`s, and `<h1></h1>`s, just like in the above example.

Render methods can also return another kind of JSX: _component instances._

```JSX
class OMG extends React.Component {
  render() {
    return <h1>Whooaa!</h1>;
  }
}
 
class Crazy extends React.Component {
  render() {
    return <OMG />;
  }
}
```

In the above example, `Crazy`‘s render method `returns` an _instance_ of the `OMG` component class. You could say that `Crazy` renders an `<OMG />`.