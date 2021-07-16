# Destructuring

Destructuring lets you extract or pull out array elements or object properties and store them in variables.

It is different from the spread or rest operator, which allow you to spread out **each** and **all** iterative elements in an array or object, whereas destructuring lets you get specific elements.

It works for arrays:

```js
[a, b] = ["Hello", "Jeremy"];
```

This assigns "hello" to the `a` variable, and "Jeremy" to the `b` variable.

Another example:

```js
const numbers = [1, 2, 3];

[a, b] = numbers;
console.log(a, b); // 1,2
```

This pulls out the first two elements of the array, but not the third.

And objects:

```js
{name} = {name: 'Jeremy', age: 31};
console.log(name) // Jeremy
console.log(age) // undefines
```

This example pulls the name property out of the object and assigns it to the `name` variable.
