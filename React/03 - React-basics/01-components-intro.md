# Components intro

React is all about **components**. A component is a block of code that can combine html, css and js into a reusable component, or section of code, that can be replicated across an interface.

## How is a component built?

HTML + CSS + Javascript = a React component.

> The core components are JS and HTML, CSS plays a lesser part in React components.

## 'Declarative' approach

React used a **declarative** approach to building components.

This means that, unlike Vanilla JS where you specify where on the page you want a component to go (think insertAdjacemtHtml), in React you define a desired **_target_** state and then let React figure out the actual JS DOM instructions.

## It's just a function

Components in React are just functions. They are special functions that return JSX code. Other than that, they are just regular functions:

```js
function ExpenseItem() {
  return (
    <div>
      <h2>Expense item</h2>
    </div>
  );
}
```
