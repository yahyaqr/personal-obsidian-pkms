---
created: Sunday, December 11th 2022 - 22.00
updated: Sunday, December 11th 2022 - 22.00
---
Self-Closing Tags

Another JSX ‘gotcha’ involves _self-closing tags_.

What’s a self-closing tag?

Most HTML elements use two tags: an _opening tag_ (`<div>`), and a _closing tag_ (`</div>`). However, some HTML elements such as `<img>` and `<input>` use only one tag. The tag that belongs to a single-tag element isn’t an opening tag nor a closing tag; it’s a _self-closing tag._

When you write a self-closing tag in HTML, it is _optional_ to include a forward-slash immediately before the final angle-bracket:

``` HTML
Fine in HTML with a slash:
<br />

Also fine, without the slash:
<br>
```

But!

In JSX, you _have to_ include the slash. If you write a self-closing tag in JSX and forget the slash, you will raise an error:

```HTML
Fine in JSX:
<br />

NOT FINE AT ALL in JSX:
<br>
```