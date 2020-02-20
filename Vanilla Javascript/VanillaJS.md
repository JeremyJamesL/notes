# Vanilla JS Notes

## Closures

A **Closure** is when an inner function has access to the scope of its outer function. 

```javascript
function retirement(retirementAge) {
    var a = ' years left until retriement.';
    return function(yearOfBirth) {
        var age = 2016 - yearOfBirth;
        console.log((retirementAge - age) + a);
    }
}

var retirementAustralia = retirement(60);
retirementAustralia(1989);
```
In this example, we create a function that determines how many years until an individual can retire, depending on their age. 

The `retirement()` function is called using the `retirementAustralia` variable and has a value passed. The function declares the `a` variable and returns an **anonymous function.** As the function is returned it is popped off the execution stack. 

However, as you can see, the inner function is able to access the `retirementAge` variable and the `a` variable of its parent function, which has already returned.

**This exemplifies the Closure**

### How Closures work

> An inner function always has access to variables and parameters of its outer function, even when the outer function has returned and its execution context has finished.

Even after a function returns and the execution context is gone, the variable object still exists in memory and is accessible within the execution stack and the scope chain. 

An inner function has access to outer function's scope. 

It is called a *closure* because the inner execution context closes in on the outer variable object. 

