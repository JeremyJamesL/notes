# Splitting up components

Splitting up components into small, manageable blocks of code is best practice.

> There is no hard rule to building an old component VS adding to an existing component

For instance, for our `ExpenseItem` we have an code block for displaying dates:

```js
<div className="expense-date">
  <div className="expense-date__month">{month}</div>
  <div className="expense-date__year">{year}</div>
  <div className="expense-date__day">{day}</div>
</div>
```

This could be considered a reusable block of code in its own right, so we can put it in it's own file called `ExpenseDate.js`.

In that file we can define the `ExpenseDate` custom component:

```js
function ExpenseDate(props) {
  const month = props.date.toLocaleString("en-US", { month: "long" });
  const day = props.date.toLocaleString("en-US", { day: "2-digit" });
  const year = props.date.getFullYear();

  return (
    <div className="expense-date">
      <div className="expense-date__month">{month}</div>
      <div className="expense-date__year">{year}</div>
      <div className="expense-date__day">{day}</div>
    </div>
  );
}

export default ExpenseDate;
```

And import it into the `ExpenseItem.js` file. In there we can use the custom component:

```js
<ExpenseDate date={props.date} />
```

The date data is still stored in the `App.js` file, we are just first passing it to the `ExpenseItem` component and then forwarding it through to the `ExpenseDate` component.

Therefore we use `{props.date}` property on the `ExpenseDate` component, which is then passed as `prop` into the `ExpenseDate` component:

```js
function ExpenseDate(props) {
  const month = props.date.toLocaleString("en-US", { month: "long" });
  const day = props.date.toLocaleString("en-US", { day: "2-digit" });
  const year = props.date.getFullYear();

  return (
    <div className="expense-date">
      <div className="expense-date__month">{month}</div>
      <div className="expense-date__year">{year}</div>
      <div className="expense-date__day">{day}</div>
    </div>
  );
}

export default ExpenseDate;
```

This is how to forward data through multiple components.
