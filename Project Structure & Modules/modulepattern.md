# Module Pattern

Module Pattern is about creating separate units of code that serve a particular, independent function within a wider application, but which interact with each other when needed.

Each module has `variables` and `functions` that are only accessible from within that module so that no other code can override the data in that module. 

We will also have *public* methods that are exposed outside of the module, so that other modules can access the methods. 

This process is called **data encapsulation**.

To achieve this we use: 

1. `Closures`.
2. `IIFEs`: immediately invoked function expressions. 

```javascript
var budgetController = (function() {

    var x = 23;

    var add = function(a) {
        return x + a;
    }

    return {
        publicTest: function(b) {
            console.log(add(b));
        }
    }

})();
```

In this IIFE example, the inner variable `x` and function `add` are inaccessible outside of the scope of the `budgetController` function, which is immediately invoked. 

However, the `publicTest` function, is accessible outside of the `IIFE` as it is returned from its outer function.

The `publicTest` function has access to the variables and methods of its outer function (`x`, `add()`) even after the `IIFE` has returned. So effectively `publicTest` is accessible, however privacy of `add` and `x` are maintained. 

A `Closure` is created in this example. `add` and `x` are within the `closure`, while `publicTest` is not.

## Separation of concerns.

Code modulation means separating code into modules that operate independently and are ignorant to each others' existence. This is called *separation of concerns*.

Each part of application should be interested in doing just one thing independently. 

