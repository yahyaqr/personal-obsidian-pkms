---
created: Sunday, December 11th 2022 - 21.54
updated: Sunday, December 11th 2022 - 21.54
---
ReactDOM.render() II

Move to the right a little more, and you will see this expression:

``` JSX
document.getElementById('app')
```

You just learned that `ReactDOM.render()` makes its _first_ argument appear onscreen. But _where_ on the screen should that first argument appear?

The first argument is _appended_ to whatever element is selected by the _second_ argument.

In the code editor, select **index.html**. See if you can find an element that would be selected by `document.getElementById('app')`.

That element acted as a _container_ for `ReactDOM.render()`‘s first argument! At the end of the previous exercise, this appeared on the screen:

``` JSX
<main id="app">
	<h1>Render me!</h1>
</main>
```