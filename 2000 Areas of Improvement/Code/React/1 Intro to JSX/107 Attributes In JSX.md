---
created: Sunday, December 11th 2022 - 21.48
updated: Sunday, December 11th 2022 - 21.48
---
Attributes In JSX

JSX elements can have _attributes_, just like HTML elements can.

A JSX attribute is written using HTML-like syntax: a _name_, followed by an equals sign, followed by a _value_. The _value_ should be wrapped in quotes, like this:

```JSX
my-attribute-name="my-attribute-value"
```

Here are some JSX elements with _attributes:_

```JSX
<a href='http://www.example.com'>Welcome to the Web</a>; const title = <h1 id='title'>Introduction to React.js: Part I</h1>; 
```

A single JSX element can have many attributes, just like in HTML:

```JSX
const panda = <img src='images/panda.jpg' alt='panda' width='500px' height='500px' />;
```