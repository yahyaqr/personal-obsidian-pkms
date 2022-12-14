---
created: Sunday, December 11th 2022 - 21.56
updated: Sunday, December 11th 2022 - 21.56
---
The Virtual DOM

One special thing about `ReactDOM.render()` is that it _only updates DOM elements that have changed_.

That means that if you render the exact same thing twice in a row, the second render will do nothing:

```JSX
const hello = <h1>Hello world</h1>;

// This will add "Hello world" to the screen: 

ReactDOM.render(hello, document.getElementById('app'));

// This won't do anything at all:

ReactDOM.render(hello, document.getElementById('app'));
```

This is significant! Only updating the necessary DOM elements is a large part of what makes React so successful.

React accomplishes this thanks to something called _the virtual DOM._ Before moving on to the end of the lesson, [read this article about the Virtual DOM](https://www.codecademy.com/articles/react-virtual-dom).