---
created: Sunday, December 11th 2022 - 22.09
updated: Sunday, December 11th 2022 - 22.09
---
JSX Conditionals: If Statements That Do Work

How can you write a _conditional_, if you can’t inject an `if` statement into JSX?

Well, one option is to write an `if` statement, and _not_ inject it into JSX.

Look at **if.js**. Follow the `if` statement, all the way from line 6 down to line 18.

**if.js** works, because the words `if` and `else` are _not_ injected in between JSX tags. The `if` statement is on the outside, and no JavaScript injection is necessary.

This is a common way to express conditionals in JSX.

---

```JSX
let message;

if (user.age >= drinkingAge) {
  message = (
    <h1>
      Hey, check out this alcoholic beverage!
    </h1>
  );
} else {
  message = (
    <h1>
      Hey, check out these earrings I got at Claire's!
    </h1>
  );
}

ReactDOM.render(
  message, 
  document.getElementById('app')
);
```