# Passing data via props

We can make components re-usable by using parameters (just like in function arguments in regular JS) and props.

We can pass data to custom components by adding attributes to them. This concept is just called 'props' (short for properties).

In order to do this we define the variables we want to use within App.js, NOT in the custom component. For instance:

```js
function App() {
  const expenses = [
    {
      id: "e1",
      title: "Toilet Paper",
      amount: 94.12,
      date: new Date(2020, 7, 14),
    },
    {
      id: "e2",
      title: "New TV",
      amount: 799.49,
      date: new Date(2021, 2, 12),
    },
  ];

  return (
      <ExpenseItem
        title={expenses[0].title}
        amount={expenses[0].amount}
        date={expenses[0].date}
      ></ExpenseItem>
      <ExpenseItem
        title={expenses[1].title}
        amount={expenses[1].amount}
        date={expenses[1].date}
      ></ExpenseItem>
  )
}
```

The attribute names (title, amount, date) here are trivial.

Then within the custom component we get access to `ExpenseItem` attributes by passing an inbuilt argument to the `ExpenseItems` function paramater. It is commonly called `props`, but the name is arbitrary.

```js
function ExpenseItem(props) {
  return (
    <div className="expense-item">
      <div>{props.date.toISOString()}</div>
      <div className="expense-item__description">
        <h2>{props.title}</h2>
        <div className="expense-item__price">{props.amount}</div>
      </div>
    </div>
  );
}
```

This is how you can pass data between components in React.
