---
created: Monday, December 12th 2022 - 06.40
updated: Monday, December 12th 2022 - 06.40
---
Apply a Component in a Render Function

This is new territory! You’ve never seen a component rendered by another component before.

You _have_ seen a component rendered before, though, but not by another component. Instead, you’ve seen a component rendered by `ReactDOM.render()`.

When a component renders another component, what happens is very similar to what happens when `ReactDOM.render()` renders a component.

---

```JSX
// ProfilePage.js

import React from 'react';
import ReactDOM from 'react-dom';
import { NavBar } from './NavBar';


class ProfilePage extends React.Component {
  render() {
    return (
      <div>
        <NavBar />
        <h1>All About Me!</h1>
        <p>I like movies and blah blah blah blah blah</p>
        <img src="https://content.codecademy.com/courses/React/react_photo-monkeyselfie.jpg" />
      </div>
    );
  }
}

ReactDOM.render(<ProfilePage />, document.getElementById('app'));
```

```JSX
// NavBar.js

import React from 'react';

export class NavBar extends React.Component {
  render() {
    const pages = ['home', 'blog', 'pics', 'bio', 'art', 'shop', 'about', 'contact'];
    const navLinks = pages.map(page => {
      return (
        <a href={'/' + page}>
          {page}
        </a>
      )
    });

    return <nav>{navLinks}</nav>;
  }
}
```