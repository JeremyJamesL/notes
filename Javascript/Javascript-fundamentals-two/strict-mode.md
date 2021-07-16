# Strict mode

```strict mode``` is a way to 'opt-in' to writing stricter Javascript code, rather than 'sloppy' Javascript code. 

It is a simple declaration at the top of a .js file:

```javascript
'use strict'
```
It can be used at a block or function level, but it most commonly used at an app of file level. 

It must be written at the beginning of a file to be apply to the whole file.

## What does strict mode do?

1. Prevents 'silent' errors by throwing an error in the console. For instance, it will throw an error for an undeclared variable (without a let, const, var statement):

```javascript
const hasDriversLicense = false;
let passedTest = true;
if(passedTest) hasDriverLicense = true;
```
This throw an 'undeclared variable' error in the console as missing the 's' in the ```hasDriverLicense``` means we are essentially declaring a new variabe, however, without a var, let, const statement. 

2. Restricts use of certain variable names that may be used in future ECMAScript releases, such as ```interface``` or ```private```.