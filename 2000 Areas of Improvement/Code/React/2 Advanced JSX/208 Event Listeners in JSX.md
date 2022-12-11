---
created: Sunday, December 11th 2022 - 22.06
updated: Sunday, December 11th 2022 - 22.06
---
Event Listeners in JSX

JSX elements can have _event listeners_, just like HTML elements can. Programming in React means constantly working with event listeners.

You create an event listener by giving a JSX element a special _attribute_. Here’s an example:

```JSX
<img onClick={myFunc} />
```

An event listener attribute’s _name_ should be something like `onClick` or `onMouseOver`: the word `on`, plus the type of event that you’re listening for. You can see a list of valid event names [here](http://facebook.github.io/react/docs/events.html#supported-events).

An event listener attribute’s _value_ should be a function. The above example would only work if `myFunc` were a valid function that had been defined elsewhere:

```JSX
function myFunc() {
	alert('Make myFunc the pFunc... omg that was horrible i am so sorry');
}

<img onClick={myFunc} />
```

Note that in HTML, event listener _names_ are written in all lowercase, such as `onclick` or `onmouseover`. In JSX, event listener names are written in camelCase, such as `onClick` or `onMouseOver`.