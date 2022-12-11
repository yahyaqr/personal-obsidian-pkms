Keys

When you make a list in JSX, sometimes your list will need to include something called `keys`:

```JSX
<ul>
  <li key="li-01">Example1</li>
  <li key="li-02">Example2</li>
  <li key="li-03">Example3</li>
</ul>
```

A `key` is a JSX attribute. The attribute’s _name_ is `key`. The attribute’s _value_ should be something unique, similar to an `id` attribute.

`keys` don’t do anything that you can see! React uses them internally to keep track of lists. If you don’t use keys when you’re supposed to, React might accidentally scramble your list-items into the wrong order.

Not all lists need to have `keys`. A list needs `keys` if either of the following are true:

1.  The list-items have _memory_ from one render to the next. For instance, when a to-do list renders, each item must “remember” whether it was checked off. The items shouldn’t get amnesia when they render.
    
2.  A list’s order might be shuffled. For instance, a list of search results might be shuffled from one render to the next.
    

If neither of these conditions are true, then you don’t have to worry about `keys`. If you aren’t sure then it never hurts to use them!

---

```JSX
const people = ['Rowe', 'Prevost', 'Gare'];

const peopleLis = people.map((person, i) =>
  // expression goes here:
  <li key={'person_'+i}>{person}</li>
);

// ReactDOM.render goes here:
ReactDOM.render(<ul>{peopleLis}</ul>, document.getElementById('app'));
```