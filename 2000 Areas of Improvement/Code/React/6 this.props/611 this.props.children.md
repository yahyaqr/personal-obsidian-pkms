this.props.children

Every component’s `props` object has a property named `children`.

`this.props.children` will return everything in between a component’s opening and closing JSX tags.

So far, all of the components that you’ve seen have been _self-closing tags_, such as `<MyComponentClass />`. They don’t have to be! You could write `<MyComponentClass></MyComponentClass>`, and it would still work.

`this.props.children` would return everything in between `<MyComponentClass>` and `</MyComponentClass>`.

Look at **BigButton.js**. In _Example 1,_ `<BigButton>`‘s `this.props.children` would equal the text, “I am a child of BigButton.”

In _Example 2,_ `<BigButton>`‘s `this.props.children` would equal a `<LilButton />` component.

In _Example 3,_ `<BigButton>`‘s `this.props.children` would equal `undefined`.

If a component has more than one child between its JSX tags, then `this.props.children` will return those children in an array. However, if a component has only one child, then `this.props.children` will return the single child, _not_ wrapped in an array.

--- 

```JSX
// BigButton.js

import React from 'react';
import { LilButton } from './LilButton';

class BigButton extends React.Component {
  render() {
    console.log(this.props.children);
    return <button>Yo I am big</button>;
  }
}


// Example 1
<BigButton>
  I am a child of BigButton.
</BigButton>


// Example 2
<BigButton>
  <LilButton />
</BigButton>


// Example 3
<BigButton />
```

```JSX
// App.js

import React from 'react';
import ReactDOM from 'react-dom';
import { List } from './List';

class App extends React.Component {
  render() {
    return (
      <div>
        <List type='Living Musician'>
          <li>Sachiko M</li>
          <li>Harvey Sid Fisher</li>
        </List>
        <List type='Living Cat Musician'>
          <li>Nora the Piano Cat</li>
        </List>
      </div>
    );
  }
}

ReactDOM.render(
  <App />, 
  document.getElementById('app')
);
```

```JSX
// List.js

import React from 'react';

export class List extends React.Component {
  render() {
    let titleText = `Favorite ${this.props.type}`;
    if (this.props.children instanceof Array) {
    	titleText += 's';
    }
    return (
      <div>
        <h1>{titleText}</h1>
        <ul>{this.props.children}</ul>
      </div>
    );
  }
}
```