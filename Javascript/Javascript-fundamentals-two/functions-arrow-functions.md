# Arrow Functions

Arrow functions is a third type of function (other than **declarations** and **expressions**) that was added in ES6.  

Arrow functions are just a simplified version of a function expression and are faster to write.

Example:

```javascript
birthYear => 2021 - birthYear;
```

This is an example of a simple arrow function, which then must be assigned to a variable as a function expresssion.

* Note that we don't need the curly brackets {}
* The return statement is ***implied*** and doesn't need to be written.
* Arrow functions are ideal for single line functions, like the below:

```javascript
const calcAge2 = birthYear => 2021 - birthYear;
calcAge2(1989);
```
The expression is now stored in the ```calcAge2``` variable.

The above is the simplest form, as we only have one ***parameter*** and one line ofcode in the function.

## More complex arrow functions

```javascript
const yearsUntilRetirement = birthYear => {
    const age = 2021 - birthYear;
    const retirement = 65 - age;
    return retirement;
}

console.log(yearsUntilRetirement(1989));
```

* For more than one line of code, curly brackets must be used{}
* A ```return``` statement must also be included, as it is not implied in a multi-line function
  
```javascript
const yearsUntilRetirement = (birthYear, firstName) => {
    const age = 2021 - birthYear;
    const retirement = 65 - age;
    return `${firstName} has ${retirement} years until retirement`;
}

console.log(yearsUntilRetirement(1989, 'Jeremy'));
```
We have to return to using brackets around our parameters when there is more than one. 

> REMEMBER: Arrow functions do not get a 'this' keyword

## When to use arrow functons?

Arrow function are great for simple, one line functions. 