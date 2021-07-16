# Rest & Spread Operators

The rest & spread operators are denoted by three dots `...` Where we use them indicates whether they are `spread` or `rest` operators.

**Spread**: use to split up array elements OR object properties.

E.g:

```js
const newArray = [...oldArray, 1, 2];
```

```js
const numbers = [1, 2, 3];
const newNumbers = [...numbers, 4];

console.log(newNumbers); // 1,2,3,4
```

This will give the `newArray` the values from the `oldArray`, plus an additional 2 values (1 and 2);

Similarly for an object:

```js
const newObject = { ...oldObject, newProp: 5 };
```

**Rest**: Used to merge a list of function arguments into an array. E.g:

```js
const filter = (...args) => {
  return args.filter((el) => el === 1);
};

console.log(filter(1, 1, 2, 3)); // [1, 1]
```
