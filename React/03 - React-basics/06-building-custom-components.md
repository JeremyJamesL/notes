# Building custom components

It's considered good practice to put new components into new files.

> One file per component is standard

Again, React components are just functions that return special JSX code

```js
function expenseItem() {
  return (
    <div>
      <h2>Expense items</h2>
    </div>
  );
}
```

That can then be exported:

```js
export default ExpenseItem;
```

And imported:

```js
import ExpenseItem from "./components/ExpenseItem";
```

And used:

```js
<ExpenseItem></ExpenseItem>
```

> Custom components must start with uppercase character when using in JSX code. The simple rule is lowercase elements are html elements, whereas uppercase elements are ones defined by developers

> If your custom component doesn't have anything between the opening and closing tags, then you can just write it as: <Expenseitem />
