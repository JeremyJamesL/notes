# Javascript versions: ES5, ES6+ and ESNext

## Brief history of JS:

**1995**: Brendan Eich created first version of JS in 10 days. Was called ***Mocha***

**1996**: Name changed to Javascript in order to attract Java developers.

**1997**: Javascript was standardised and made into official stadard by ECMA.

**2009**: ES5 (ECMAScript 5) was released.

**2015**: ES6 / ES2015 (ECMAScript 2015) was released, being the biggest update to the language to date. 

This was when an ***annual release cycle*** was introduced, hence the '2015'.

**2016 - the end of time**: There will be a new release every year

## Backwards compatability

Modern JS engines was interpret old JS code, written in 1997, for instance. Making it backwards compatible. 

This means nothing is ever really removed, just added:

1. Old features are never removed
2. New versions aren't really ***versions***, more so incremental updates or releases.
3. This prevents breaking the web, allowing old websites to never break. 

## Forwards compatability 

JS isn't forwards compatible, meaning new code can't run in outdated browsers (users may use outdated browser versions, for instance). Therefore:

1. **During development** test code using up-to-date browsers. 
2. **Production**: When app is deployed, if we have written modern JS that doesn't run on an outdated browser, we need to transpile code and polyfill our code converting it back to old versions of JS [ES5, for instance] to ensure browser compatability for all users.

## ES5 

1. Fully supported in all browsers (downt o IE 9 from 2011)
2. Ready to be used today

## ES2015 -> ES2020 (ES6+)

1. Well supported in all modern browsers.
2. No support in old browsers.
3. Can use most features in production wit transpiling and polyfilling.


[ES6 compatibility table](https://kangax.github.io/compat-table/es6/)

## Future releases (ESNext)

1. Future versons of the language (new feature proposals)
2. Can already use some features in production with transpiling and polyfilling. 


## Learning old JS

Is important to better understand how the language works. A lot of online tutorials will be written in ES5.

Some old codebases will be written in ES5 as well.