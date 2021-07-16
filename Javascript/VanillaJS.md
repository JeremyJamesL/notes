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


## Bind, Call and Apply

Functions inherit these special methods from the function constructor object.

These methods allow us to call a function and set the `this` variable manually.

### Call

The `Call` method allows for method *borrowing*. 

The follow is a simple person object with a method. The method will be for the person to introduce themselves, with a `timeOfDay` and `style` parameters. Output will depend on the style of speech.

```javascript

var john = {
    name: 'John',
    age: 26,
    job: 'teacher',
    presentation: function(timeOfDay, style){
        if(style == 'formal') {
            console.log('Good ' + timeOfDay + ' , my name is ' + this.name + ' and my occupation is ' + this.job + ' I am ' + this.age + '. I hope you have a lovely' + timeOfDay);
        } else if(style === 'casual') {
            console.log('Hey! What\'s up?, My name is' + this.name + ' I work as a ' + this.job + 'and I hope you have a wicked' + timeOfDay);
        }
    }
    

```
If another object wanted to borrow the `john.presentation` method, then the `call` method can be used

```javascript
var emily = {
    name: 'Emily',
    job: 'social worker'
}

john.presentation.call(emily, 'casual', 'afternoon')
```

Output:
*Hey! What's up?, My name is Emily I work as a social worker. I hope you have a wicked morning.*

> The call method allows us to set the `this` variable in the first argument. 

### Apply

> `Apply` is similar to the `call` method, except it accepts arguments as an `array`.


### Bind

> Bind is also similar to `call`, allowing us to explicitly set the `this` variable. `Bind`, however, doesn't immediately call the function, but generates a copy of the function to be stored somewhere. 

This allows us to create arguments with pre-set arguments:

```javascript
var johnMorning = john.presentation.bind(john, 'morning');

johnMorning('friendly');
```
Output:
*Hey! what's up? I'm John , I'm a teacher and i'm 26 years old. Have a nice morning*

In this example, we are storing the function in a variable `johnFriendly` to be called later. We are setting the `this` variable to `john` and we are pre-setting the first argument to `morning`.

When the function is called using `johnMorning('friendly')` , we are calling the function with the remaining missing parameter that wasn't pre-set.

This allows us to create a version of a function, in this case always with the "morning" version. 

> This technique is called `currying`: creating function based on another function, but with some preset parameters.

