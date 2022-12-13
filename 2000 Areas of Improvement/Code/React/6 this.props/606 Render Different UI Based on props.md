---
created: Monday, December 12th 2022 - 21.08
updated: Monday, December 12th 2022 - 21.08
---
Render Different UI Based on props

Awesome! You passed a prop from a component to a different component, accessed that prop from the receiver component, and rendered it!

You can do more with `props` than just display them. You can also use `props` to make decisions.

In the code editor, look at the `Welcome` component class.

You can tell from `this.props.name` on line 5 that `Welcome` expects to receive a piece of information called _name_. However, `Welcome` never renders this piece of information! Instead, it uses the information to make a decision.

`<Welcome />` instances will render the text `WELCOME "2" MY WEB SITE BABYYY!!!!!`, unless the user is Mozart, in which case they will render the more respectful  
`hello sir it is truly great to meet you`  
`here on the web`.

The passed-in _name_ is not displayed in either case! The name is used to _decide_ what will be displayed. This is a common technique.

Select **Home.js** and look at the `Home` component class. What will `<Welcome />` render to the screen?

---

```JSX
// App.js

import React from 'react';
import ReactDOM from 'react-dom';
import { Greeting } from './Greeting';

class App extends React.Component {
  render() {
    return (
      <div>
        <h1>
          Hullo and, "Welcome to The Newzz," "On Line!"
        </h1>
        <Greeting name="Alison" signedIn={true} />
        <article>
          Latest:  where is my phone?
        </article>
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
// Welcome.js

import React from 'react';

export class Welcome extends React.Component {
  render() {
    if (this.props.name === 'Wolfgang Amadeus Mozart') {
      return (
      	<h2>
      	  hello sir it is truly great to meet you here on the web
      	</h2>
      );
    } else {
      return (
      	<h2>
      	  WELCOME "2" MY WEB SITE BABYYY!!!!!
      	</h2>
      );
    }
  }
}
```

```JSX
// Home.js

import React from 'react';
import ReactDOM from 'react-dom';
import { Welcome } from './Welcome';

class Home extends React.Component {
  render() {
    return <Welcome name='Ludwig van Beethoven' />;
  }
}

ReactDOM.render(
  <Home />, 
  document.getElementById('app')
);
```

```JSX
// Greeting.js

import React from 'react';
import ReactDOM from 'react-dom';

export class Greeting extends React.Component {
  render() {
  	if (this.props.signedIn === false) {
  	  return <h1>GO AWAY</h1>;
  	} else {
  	  return <h1>Hi there, {this.props.name}!</h1>;
  	}
  }
}
```