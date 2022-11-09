---
created: Sunday, October 30th 2022 - 01.55
updated: Sunday, October 30th 2022 - 01.55
---
### Import React and ReactDOM
```JSX
import React from 'react';
import ReactDOM from 'react-dom';
```

### Inline JSX Elements
```JSX
const title = <h1>Welcome all!</h1>;
```

### Nested JSX Elements
In order for the code to compile, a JSX expression must have exactly one outermost element. In the below block of code the `<a>` tag is the outermost element.
```JSX
const myClasses = (
  <a href="https://www.codecademy.com">
    <h1>
      Sign Up!
    </h1>
  </a>
);
```

### Empty JSX Elements
In JSX, empty elements must explicitly be closed using a closing slash at the end of their tag: `<tagName />`.
```JSX
<br />
<img src="example_url" />
```

### Class renamed to className
```JSX
// When rendered, this JSX expression...
const heading = <h1 className="large-heading">Codecademy</h1>;

// ...will be rendered as this HTML
<h1 class="large-heading">Codecademy</h1>
```

### JSX Key Attribute
In JSX elements in a list, the `key` attribute is used to uniquely identify individual elements. It is declared like any other attribute. Keys can help performance because they allow React to keep track of whether individual list items should be rendered, or if the order of individual items is important.
```JSX
<ul>
  <li key="key1">One</li>
  <li key="key2">Two</li>
  <li key="key3">Three</li>
  <li key="key4">Four</li>
</ul>
```

### Render JSX Elements
#### Inline
```JSX
ReactDOM.render(<h1>Render me!</h1>, document.getElementById('app'));
```
#### Multiline
```JSX
ReactDOM.render(
  <h1>This is an example.</h1>, 
  document.getElementById('app')
);
```

### Embedding JS in JSX
#### Inline
```JSX
let expr = <h1>{10 * 10}</h1>;
```
#### Multiline
```JSX
const tasty = (
  <ul>
    <li>Applesauce</li>
    { !baby && <li>Pizza</li> }
    { age > 15 && <li>Brussels Sprouts</li> }
    { age > 20 && <li>Oysters</li> }
    { age > 25 && <li>Grappa</li> }
  </ul>
);
```

### Event Listeners in JSX
```JSX
// Basic example
const handleClick = () => alert("Hello world!");
const button = <button onClick={handleClick}>Click here</button>;

// Example with event parameter
const handleMouseOver = (event) => event.target.style.color = 'purple';
const button2 = <div onMouseOver={handleMouseOver}>Drag here to change color</div>;
```

### The .map() array method in JSX
If you want to create a list of JSX elements from a given array, then map() over each element in the array, returning a list item for each one.
```JSX
const arrayOfStrings = ['Home', 'Shop', 'About Me'];

const listItems = arrayOfStrings.map(string => <li>{string}</li>);

<ul>{listItems}</ul>
```