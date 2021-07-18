# 12. The concept of "composition" ("childen props")

The concept of building a UI from smaller building blocks is called **composition**.

Sometimes we may want to wrap out building blocks in a containing, or 'shell' component. For instance, if we wanted to wrap our whole app in a component called `Card`, whose stylining can be inherited by child elements, we could create a custom component purely for that purpose:

```js
import "./Card.css";

function Card() {
  return <div className="card"></div>;
}

export default Card;
```

```js
function ExpenseItem(props) {
  return (
    <Card className="expense-item">
      <ExpenseDate date={props.date} />
      <div className="expense-item__description">
        <h2>{props.title}</h2>
        <div className="expense-item__price">{props.amount}</div>
      </div>
    </Card>
  );
}
```

However,out of the box this doesn't work and nothing will be shown in the UI. While it works for HTML elements, it doesn't automatically work to wrap out components in a shell.

It is achievable by using a special `prop` that is built into React. That is `{props.children}`.

```js
function Card(props) {
  return <div className="card">{props.children}</div>;
}
```

> Every custom component has the special `children` prop, whether we use it or not.

> Note: `children` is a reserved name in React.
