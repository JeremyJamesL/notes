# Outputting dynamic data & expressions

We don't just want to have one component we can output, like our expenseItem example.

We want to have multiple, each with different data and outputs. To do this, we have to dynamically output data, so that not all our JSX code is hardcoded.

For instance, in our expenseItem example:

```js
function ExpenseItem() {
  return (
    <div className="expense-item">
      <div>March 28, 2021</div>
      <div className="expense-item__description">
        <h2>Car Insurance</h2>
        <div className="expense-item__price">$249.67</div>
      </div>
    </div>
  );
}
```

The date, price etc should all be dynamic.

## Dynamic data in JSX

Hardcoding the date etc above isn't ideal, so just like in normal JS, we can define variables, which we can then use in place of the hardcoded data.

We can do this before the function is returned, e.g:

```js
function ExpenseItem() {
  const expenseDate = new Date(2021, 2, 28);
  const expenseTitle = "Car Insurance";
  const expenseAmount = 297.67;

  return (
    <div className="expense-item">
      <div>March 28, 2021</div>
      <div className="expense-item__description">
        <h2>Car Insurance</h2>
        <div className="expense-item__price">$249.67</div>
      </div>
    </div>
  );
}
```

To output this data in the return statement we can use special JSX syntax denoted by curly braces `{}`. These braces let us run expressions to output dynamic data, for instance you could do: `{1+1}` and the output will be `2`.

We can also refer to the values referred in out constants:

```js
function ExpenseItem() {
  const expenseDate = new Date(2021, 2, 28);
  const expenseTitle = "Car Insurance";
  const expenseAmount = 297.67;

  return (
    <div className="expense-item">
      <div>{expenseDate.toISOString()}</div>
      <div className="expense-item__description">
        <h2>{expenseTitle}</h2>
        <div className="expense-item__price">{expenseAmount}</div>
      </div>
    </div>
  );
}
```

Now we have dynamic placeholders, at least.
