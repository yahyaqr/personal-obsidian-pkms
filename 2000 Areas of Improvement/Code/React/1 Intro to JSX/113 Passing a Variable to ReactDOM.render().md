---
created: Sunday, December 11th 2022 - 21.55
updated: Sunday, December 11th 2022 - 21.55
---
Passing a Variable to ReactDOM.render()

`ReactDOM.render()`‘s first argument should _evaluate_ to a JSX expression, it doesn’t have to literally _be_ a JSX expression.

The first argument could also be a variable, so long as that variable evaluates to a JSX expression.

In this example, we save a JSX expression as a _variable_ named `toDoList`. We then pass `toDoList` as the first argument to `ReactDOM.render()`:

```JSX
const toDoList = (
	<ol>
		<li>Learn React</li>
		<li>Become a Developer</li>
	</ol>
);

ReactDOM.render(
	toDoList,
	document.getElementById('app')
);
```