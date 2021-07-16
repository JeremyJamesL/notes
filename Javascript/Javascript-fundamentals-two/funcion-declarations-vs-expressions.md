# Function declarations VS expressions

## Declaration:

```javascript
function caclAge1(birthYear) {
    return 2021 - birthYear;
}

var age1 = caclAge1(1989);
console.log(age1);

```

## Expression:

```javascript
const calcAge2 = function (birthYear) {
    return 2021 - birthYear;
}

var age2 = calcAge2(1989);
console.log(age2);

```

The function in this case is an expression, which produces a value, which is then stored in the variable ```calcAge2```. Functions are just values. It is not a type, it is a value, which can be stored in a variable.


## What is the main difference?

We can call function declarations before they are defined in the code. E.g:


```javascript
var age1 = caclAge1(1989);
console.log(age1);

function caclAge1(birthYear) {
    return 2021 - birthYear;
}
```
This is because function declarations are **hoisted**. 

Expressions, on the other hand are ***not*** hoisted.

## Which type should you use?

It's really a matter of personal preference. Using function expressions, however, means you must define the functions at the top of the code before they can be called, helping organise and structure your code better.
