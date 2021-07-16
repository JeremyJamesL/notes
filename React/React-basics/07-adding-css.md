# Adding CSS to React projects

We add the .css file next to the .js file within the component's directory.

You must explicity include the .css file in your component's .js file, like so:

```js
import "./ExpenseItem.css";
```

## Adding classes to JSX

We don't add typical classes to the JSX syntax.

Instead of:

```js
<div class="class-name">
```

We use the property `className`:

```js
<div class ="className">
```
