---
created: Monday, December 12th 2022 - 06.27
updated: Monday, December 12th 2022 - 06.27
---
Use a Variable Attribute in a Component

Take a look at this JavaScript object named `redPanda`:

```JSX
const redPanda = {
  src: 'https://upload.wikimedia.org/wikipedia/commons/b/b2/Endangered_Red_Panda.jpg',
  alt: 'Red Panda',
  width: '200px
};
```

How could you render a React component, and get a picture with `redPanda`‘s properties?

Select **RedPanda.js** to see one way to do it.

Note all of the curly-brace JavaScript injections inside of the render function! Lines 16, 17, and 18 all use JavaScript injections.

You can, and often will, inject JavaScript into JSX inside of a render function.

---

```JSX
// App.js

import React from 'react';
import ReactDOM from 'react-dom';


const owl = {
  title: 'Excellent Owl',
  src: 'https://content.codecademy.com/courses/React/react_photo-owl.jpg'
};

// Component class starts here:
class Owl extends React.Component {
  render() {
    return (
      <div>
        <h1> {owl.title} </h1>
        <img src={owl.src} alt={owl.title} />
      </div>
    )
  };
};

ReactDOM.render(<Owl/>, document.getElementById('app'));
```

```JSX
// RedPanda.js

import React from 'react';
import ReactDOM from 'react-dom';

const redPanda = {
  src: 'https://upload.wikimedia.org/wikipedia/commons/b/b2/Endangered_Red_Panda.jpg',
  alt: 'Red Panda',
  width:  '200px'
};

class RedPanda extends React.Component {
  render() {
    return (
      <div>
        <h1>Cute Red Panda</h1>
        <img 
          src={redPanda.src}
          alt={redPanda.alt}
          width={redPanda.width} />
      </div>
    );
  }
}

ReactDOM.render(
  <RedPanda />,
  document.getElementById('app')
);

```