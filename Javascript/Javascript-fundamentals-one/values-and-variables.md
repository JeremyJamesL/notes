# Values & variables

A **variable** is a container for a piece of data (called a **value**).

The **variable** is simply the 'box' in which a **value** is stored. 

## Naming conventions

1. Variables can only contain letters, underscores and the $ sign. All other characters are illegal. 

2. For variables of more than one word, **camelCase** is used. e.g: 
``` javascript
let myName = 'Jeremy';
let whereIAmFrom = 'Australia';
```

3. *Hard rules to follow:*
  * Cannot use certain [reserved keywords:](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Lexical_grammar#reserved_keywords_as_of_ecmascript_2015), such as **new** or **function**.
  * **'name'** should not be used, despite being legal. 
  * Variable names should not start w/ uppercase letters (this convention is reserved for OOP).
  * UPPERCASE variables are used for **constants** that we know will not change. 
  * Keep names descriptive ``` let myFirstJob = 'marketer';  let myCurrentJob = 'developer'; ```







