# Adding vailla JS to components

You can use regular JS within custom components.

For instance, in our `ExpenseItem.js` component if we want to output the month in a human-readable format, we can:

```js
function ExpenseItem(props) {
  return (
    <div>
        <div>{props.date.toLocaleString('en-US', {month: "long"})}</div>
    </div>;
  )
}
```

We are accessing the `props` data that we have passed into our custom component in `App.js`, and then calling a method on it. The method is a regular JS method and doesn't need to be written uniquely.

However, it is best practice to store any constants, in this case the date, outside of he return statement like so:

```js
function ExpenseItem(props) {
  const month = rops.date.toLocaleString("en-US", { month: "long" });

  return (
    <div>
      <div>{month}</div>
    </div>
  );
}
```

> It's considered best practice to declare variables outside of the return statement, at the beginning of the custom component function.
