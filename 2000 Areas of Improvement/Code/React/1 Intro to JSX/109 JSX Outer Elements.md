---
created: Sunday, December 11th 2022 - 21.51
updated: Sunday, December 11th 2022 - 21.51
---
JSX Outer Elements

There’s a rule that we haven’t mentioned: a JSX expression must have exactly _one_ outermost element.

In other words, this code will work:

```JSX
const paragraphs = (
	<div id="i-am-the-outermost-element">
		<p>I am a paragraph.</p>
		<p>I, too, am a paragraph.</p>
	</div>
);
```

But this code will not work:

```JSX
const paragraphs = (
	<p>I am a paragraph.</p>
	<p>I, too, am a paragraph.</p>
);
```

The _first opening tag_ and the _final closing tag_ of a JSX expression must belong to the same JSX element!

It’s easy to forget about this rule, and end up with errors that are tough to diagnose.

If you notice that a JSX expression has multiple outer elements, the solution is usually simple: wrap the JSX expression in a `<div></div>`.