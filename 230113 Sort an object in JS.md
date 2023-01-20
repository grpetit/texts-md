# Sort an object in JS? o_0

## Sometimes concise object format may be usefull

Writing key value where key is not simple description field but define a specific value.
Consider a user with name "toto" who is 12 years old. You can write this like so:

```js
const user = {
  toto: 12,
};
```

And a list of user:

```js
const users = { toto: 12, tata: 15, titi: 4, tutu: 8 };
```

<!-- ```js
const users = [{ toto: 12 }, { tata: 15 }, { titi: 4 }, { tutu: 8 }];
``` -->

## Object fields have order

```js

```

First entry is first entry...

## Rebuild to sort

```js
listArrSorted = Object.entries(list).sort(([, a], [, b]) => a - b);
//[ [ 'titi', 4 ], [ 'tutu', 8 ], [ 'toto', 12 ], [ 'tata', 15 ] ]
listArrSorted;
//[ [ 'titi', 4 ], [ 'tutu', 8 ], [ 'toto', 12 ], [ 'tata', 15 ] ]
listSorted = listArrSorted.reduce((a, v) => ({ ...a, [v[0]]: v[1] }), {});
//{ titi: 4, tutu: 8, toto: 12, tata: 15 }
```

## Keep data as standard as possible

This can be used for optimisation.
Nevertheless, array must have same structured data bécasse apply algorithmes on array must be scalable.
As a clean code, a list of user contains user object. User object is define by field description.

You write this array like:

```js
const users = [
  { name: 'toto', age: 12 },
  { name: 'Tata', age: 15 },
  { name: 'Titi', age: 4 },
  { name: 'Tutu', age: 8 },
];
```

And sort directly:

## Object vs Array vs Set

### Set

Set objects are collections of values. You can iterate through the elements of a set in insertion order. A value in the Set may only occur once; it is unique in the Set's collection

## Why

```js
list = [
  {
    name: 'toto',
    age: 12,
  },
  {
    name: 'tata',
    age: 15,
  },
  {
    name: 'titi',
    age: 4,
  },
  {
    name: 'tutu',
    age: 8,
  },
];
```

```js
list = {
  toto: 12,
  tata: 15,
  titi: 4,
  tutu: 8,
};
//{ toto: 12, tata: 15, titi: 4, tutu: 8 }
console.log(list);
//{ toto: 12, tata: 15, titi: 4, tutu: 8 }
listArrSorted = Object.entries(list).sort(([, a], [, b]) => a - b);
//[ [ 'titi', 4 ], [ 'tutu', 8 ], [ 'toto', 12 ], [ 'tata', 15 ] ]
listArrSorted;
//[ [ 'titi', 4 ], [ 'tutu', 8 ], [ 'toto', 12 ], [ 'tata', 15 ] ]
listSorted = listArrSorted.reduce((a, v) => ({ ...a, [v[0]]: v[1] }), {});
//{ titi: 4, tutu: 8, toto: 12, tata: 15 }
```
