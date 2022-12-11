---
created: Sunday, December 11th 2022 - 21.48
updated: Sunday, December 11th 2022 - 21.48
---
Nested JSX

You can _nest_ JSX elements inside of other JSX elements, just like in HTML.

Here’s an example of a JSX `<h1>` element, _nested_ inside of a JSX `<a>` element:

```JSX
<a href="https://www.example.com"><h1>Click me!</h1></a>
```

To make this more readable, you can use HTML-style line breaks and indentation:

```JSX
<a href="https://www.example.com">  <h1>    Click me!  </h1></a>
```

If a JSX expression takes up more than one line, then you must wrap the multi-line JSX expression in parentheses. This looks strange at first, but you get used to it:

```JSX
(
	<a href="https://www.example.com">
		<h1>
			Click me!
		</h1>
	</a>
)
```

_Nested_ JSX expressions can be saved as variables, passed to functions, etc., just like non-nested JSX expressions can! Here’s an example of a _nested_ JSX expression being saved as a variable:

```JSX
const theExample = (
	<a href="https://www.example.com">
		<h1>
			Click me!
		</h1>
	</a>
);
```