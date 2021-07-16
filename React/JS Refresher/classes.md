# Classes

Classes are blueprints for objects.

A class is created with the `class` keyword and can have both properties and methods:

```js
class Person {
    name = "Max" // Property
    call = () => {...} // Methods
}
```

Put simply, properties are `variables` attached to classes, whereas Methods are `functions` attached to classes.

Classes are instantiated with the `new` keyword, similar to constructor functions.

```js
const myPerson = new Person();
myPerson.call();
console.log(myPerson.name);
```

> Classes are a more convenient form of constructor functions

Classes also support inheritence and extensionability. e.g:

```js
class Person extends Master;
```
