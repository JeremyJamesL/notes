# Reference and Primitive Types

## Primitive types

When you store one variable into another when using primitives (numbers, strings etc), it actually copies the value, e.g:

```js
const number = 2;
const newNum = number;
```

This copies the primitive number 2 into the `newNum` variable.

## Reference

With objects, however,

```js
const person = {
  name: "Jeremy",
};

const secondPerson = person;
console.log(secondPerson); //[object Object ] { name: "Jeremy"}
```

While consolling secondPerson prints the same value, it won't have actually copied the person. Instead, it stores a reference or a pointer to the person. Therefore if it's always just storing a pointer, then changing the original object will also affect the second variable, i.e:

```js
const person = {
  name: "Jeremy",
};

const secondPerson = person;

person.name = "James";

console.log(secondPerson); //[object Object ] { name: "James"}
```

It prints James because it is just a storage of a pointer.

> The same principle works for arrays. This is important in React when it comes to copying arrays and objects. This is done by using a spread operator {...}

```js
const person = {
  name: "Jeremy",
};

const secondPerson = {
    ...person;
}

person.name = "James";

console.log(secondPerson); //[object Object ] { name: "James"}

```

> If you reassign objects and arrays, you are merely copying the pointer, not the value.
