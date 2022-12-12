---
created: Monday, December 12th 2022 - 06.34
updated: Monday, December 12th 2022 - 06.34
---
Require A File

When you use React.js, every JavaScript file in your application is invisible to every other JavaScript file by default. **ProfilePage.js** and **NavBar.js** can’t see each other.

This is a problem!

On line 9, you just added an instance of the `NavBar` component class. But since you’re in **ProfilePage.js**, JavaScript has no idea what `NavBar` means.

If you want to use a variable that’s declared in a different file, such as `NavBar`, then you have to _import_ the variable that you want. To import a variable, you can use an `import` statement:

```JSX
import { NavBar } from './NavBar.js';
```

We’ve used `import` before, but not like this! Notice the differences between the above line of code and this familiar line:

```JSX
import React from 'react';
```

The first important difference is the curly braces around `NavBar`. We’ll get to those soon!

The second important difference involves the contents of the string at the end of the statement: `'react'` vs `'./NavBar.js'`.

If you use an `import` statement, and the string at the end begins with either a dot or a slash, then `import` will treat that string as a _filepath_. `import` will follow that filepath, and import the file that it finds.

If your filepath doesn’t have a file extension, then “.js” is assumed. So the above example could be shortened:

```JSX
import { NavBar } from './NavBar';
```

**One final, important note:**  
None of this behavior is specific to React! [Module systems](http://eloquentjavascript.net/10_modules.html) of independent, importable files are a very popular way to organize code. [React’s specific module system comes from ES6](https://hacks.mozilla.org/2015/08/es6-in-depth-modules/). More on all of that later.

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