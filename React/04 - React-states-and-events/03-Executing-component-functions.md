# 4.3 Executing component functions & State

We have our `clickHandler` function:

```js
const clickHandler = () => {
  console.log("do something");
};
```

Which is pointed at by our custom component using a prop:

```js
<button onClick={clickHandler}>Change Title</button>
```

We could assume that dynamically changing a DOM element would work, i.e:

```JSX
const ExpenseItem = (props) => {
  let title = props.title;

  const clickHandler = () => {
    title = "Updated!";
  };

  return (
    <Card className="expense-item">
      <ExpenseDate date={props.date} />
      <div className="expense-item__description">
        <h2>{title}</h2>
        <div className="expense-item__price">${props.amount}</div>
      </div>
      <button onClick={clickHandler}>Change Title</button>
    </Card>
  );
};
```

But this doesn't work, because of how React parses JSX code:

## How React parses JSX

React parses JSX sequentially. It encounters a custom component (which is just a function) such as `<App/>` executes it, discovers `<Card />` within `<App/>` and executes it, it then finds `<ExpenseItem/>` in `<Card />` and executes that function. So on and so on...

The final result is the code painted to the screen. That's it's job done.

It can't, however, know from our `ClickHandler` function to change something on the screen, because React has already painted the JSX code to the screen and done its job.

So solve this, we use [State](./04-State-and-useState.md).
