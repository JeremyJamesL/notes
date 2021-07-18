# 4.2: Event Listeners and Event Handlers

On html elements we have access to all native DOM events.

For all default events in html regular JS (like click, blur etc etc) we have `props` that allow us to listen to events.

In JS this is achieved through an imperative approach, e.g get this element, wait for a click, then perform an action.

```js
document.querySelector(".selector").addEventListener("click", function () {
  /// Do something
});
```

The React imperative approach is thusly:

```js
<Card>
    <button onClick="function to go here">Change Title</button>
<Card />
```

So React exposes the eventhandlers for us to pass as props on JSX elements, here we are passing `onClick`. We then define code that is executed onClick using a function.

We can pass anonymous, inline functions:

```js
<Card>
    <button onClick="{() => {console.log('clicked')}}">Change Title</button>
<Card />
```

However, this isn't best practice. We want JSX code lean and not put too much logic in it, we want to define it outside of the JSX code:

```js
const ExpenseItem = (props) => {
  const clickHandler = () => {
    console.log("Clicked!!!");
  };

  return (
    <Card className="expense-item">
      <ExpenseDate date={props.date} />
      <div className="expense-item__description">
        <h2>{props.title}</h2>
        <div className="expense-item__price">${props.amount}</div>
      </div>
      <button onClick={clickHandler}>Change Title</button>
    </Card>
  );
};
```

## Some rules:

> All event handler props want a function passed as a value

> Note that we don't CALL the function within the `button` prop, but instead just point to the `clickHandler` function. If we called it, then the function would run as soon as the JSX code is parsed, which would be too soon.

> It's common to end event handler funtions it is common to end them with 'Handler'.

> The event props (onClick) are camelCase.
