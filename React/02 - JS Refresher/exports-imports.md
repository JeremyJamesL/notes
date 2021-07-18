# Exports and Imports (Modules)

Next Gen JS lets us write modular JS code by letting us split it up into multiple files. It is heavily used in React.

The idea behind `import` and `export` statements is to allow us to import content from one file into another file.

E.g:

A file called person.js

```js
const person = {
    name: 'Jeremy';
}

export default person
```

`Default` keyword marking this as the default export of the file. Whatever it imported from this file will be the person object.

A second file called utility.js:

```js
export const clean = () => {...};

export const baseData = 10;
```

A third file called app.js, which imports the code from the previous two files:

```js
import person from "./person.js";
import prs from "./person.js"; // Can name whatever as it is the default export from person.js

import { baseData } from "./utility.js"; // Exact name must be imported for named exports
import { clean } from "./utility.js";
```

The imports from utility.js are so called **named exports** and are wrapped in `{}`;

> This next Gen feature will not run in all modern browsers and will need to be compiled into current gen JS features.
