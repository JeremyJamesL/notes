# Data types

All data in JS is either:

1. An **object**
2. A **primitive**

## Primitives

Primitives consists of 7 data types:

1. **Number**: Floating point numbers, that always contain a decimal, even if not visible: ```let age = 23 // Same as 23.0```.
2. **String**: Simply a sequence of characters. Strings must be encapsulated in single(' ') or double(" ") quotes. 
3. **Boolean**: either *true* or *false*. Used decision making. 
4. **Undefined**: value taken by a variable that is not yet defined. i.e
``` javascript
let empty; // evaluates to value 'undefined' 
```
5. **Null**: Similar to undefined, but is the *intentional* absence of an object value.

6. **Symbol(introduced in ES2015):** A unique value that cannot be changed.

7. **BigInt(introduced in ES2020):** Large numbers that the **number** data type can't hold. 

## Dynamic typing

Javascript has *dynamic typing*, which means that the data type doesn't need to be declared (unlike other programming languages) and occurs automatically. 

The variable itself doesn't hold the data type, it is the value that holds the data type.

This means the value data type can be changed automatically:

``` javascript
let puppy = true;
puppy = 'spot';
console.log(typeof puppy); // string
```

The data type of the ```puppy``` value is automatically changed;

### typeof

```typeof``` allows you to see the data type of the value (not the variable, as noted above).
``` javascript
let age = 23;
let myHometown = "Sydney";
let noValue;
console.log(typeof age); // number
console.log(typeof myHometown); // string
console.log(typeof age); // undefined
```

#### A note on undefined:

The value and the data type of a variable can be both undefined:

``` javascript
let year;
console.log(year); // undefined
console.log(typeof year); // undefined
```

This means that the value of the variable is undefined, and its data type is also undefined.