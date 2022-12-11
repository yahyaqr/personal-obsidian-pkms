---
created: Sunday, December 11th 2022 - 22.16
updated: Sunday, December 11th 2022 - 22.16
---
React.createElement

You can write React code without using JSX at all!

The majority of React programmers do use JSX, and we will use it for the remainder of this tutorial, but you should understand that it is possible to write React code without it.

The following JSX expression:

```JSX
const h1 = <h1>Hello world</h1>;
```

can be rewritten without JSX, like this:

```JSX
const h1 = React.createElement(
  "h1",
  null,
  "Hello world"
);
```

When a JSX element is compiled, the compiler _transforms_ the JSX element into the method that you see above: `React.createElement()`. Every JSX element is secretly a call to `React.createElement()`.

We won’t go in-depth into how `React.createElement()` works, but you can start with the [documentation](http://facebook.github.io/react/docs/top-level-api.html#react.createelement) if you’d like to learn more!