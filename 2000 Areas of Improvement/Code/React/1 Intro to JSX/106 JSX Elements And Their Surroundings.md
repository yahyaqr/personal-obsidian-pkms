---
created: Sunday, December 11th 2022 - 21.45
updated: Sunday, December 11th 2022 - 21.45
---
JSX Elements And Their Surroundings

JSX elements are treated as JavaScript _expressions_. They can go anywhere that JavaScript expressions can go.

That means that a JSX element can be saved in a variable, passed to a function, stored in an object or array…you name it.

Here’s an example of a JSX element being saved in a variable:

```JSX
const navBar = <nav>I am a nav bar</nav>;
```

Here’s an example of several JSX elements being stored in an object:

```JSX
const myTeam = {
	center: <li>Benzo Walli</li>,
	powerForward: <li>Rasha Loa</li>,
	smallForward: <li>Tayshaun Dasmoto</li>,
	shootingGuard: <li>Colmar Cumberbatch</li>,
	pointGuard: <li>Femi Billon</li>
};
```