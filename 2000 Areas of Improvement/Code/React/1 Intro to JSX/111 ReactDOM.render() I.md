ReactDOM.render() I

Let’s examine the code that you just wrote in the last exercise.

```JSX
ReactDOM.render(<h1>Render me!</h1>, document.getElementById('app'));
```

You can see something called `ReactDOM`. What’s that?

`ReactDOM` is the name of a JavaScript library. This library contains several React-specific methods, all of which deal with [the DOM](http://www.w3schools.com/js/js_htmldom.asp) in some way or another.

We’ll talk more later about how `ReactDOM` got into your file. For now, just understand that it’s yours to use.

Move slightly to the right, and you can see one of `ReactDOM`‘s methods: `ReactDOM.render()`.

`ReactDOM.render()` is the most common way to _render_ JSX. It takes a JSX expression, creates a corresponding tree of DOM nodes, and adds that tree to the DOM. That is the way to make a JSX expression appear onscreen.

Move to the right a little more, and you come to this expression:

```JSX
<h1>Hello world</h1>
```

This is the first _argument_ being passed to `ReactDOM.render()`. `ReactDOM.render()`‘s first argument should be a JSX expression, and it will be rendered to the screen.

We’ll discuss the second argument in the next exercise!