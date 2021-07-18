# Working with State

## Why regular eventHandling doesn't work

State is a way to re-evaluate a component and repaint it on the screen. It adds **_reactivity_**.

In our `ClickHandler` example, the `title` within the `<Card/>` element must be reevaluated and repainted.

The regular variable in our example:

```js
let title = props.title;
```

Which we want to be re-evaluated by React, is simply ignored, because React doesn't care about regular variables like that.

> If you have a variable in your component variable in your component function and that variable changes, React ignores it. It executes, but the overall component function (the custom component) doesn't change.

## 'useState'

To solve this problem we have to import a special element from the react library, called `useState`, which is a function.

```JSX
import React, {useState} from "react";
```

> `useState` lets us define values as `state`, where changes to these values will reflect in the component function.

## Using 'useState'

Inside our component function we just call `useState()`.

> **`useState` is a hook, all hooks start with 'use' and must be called from within component functions**

Whenever you have an element that needs updating in the UI, you must use `useState()`.

We use it like this:

1. We declare a new state variable, which we'll call 'title'. You then pass the value you want changed into the `useState` hook (`props.title`).

```JSX
const [title] = useState(props.title)
```

2. `useState` always returns a pair of values, the current state and a function that updates it. So we use destructuring to first set the state `title` (whose value `props.title` is passed into `useState`) and then pass a function that will update the state:

```JSX
const [title, setTitle] = useState(props.title);
```

3. We can then call the `setTitle` function with the new value:

```JSX
const [title, setTitle] = useState(props.title);
```

4. Final result:

```JSX
const ExpenseItem = (props) => {
  const [title, setTtle] = useState(props.title);


  const clickHandler = () => {
    setTitle('Update');
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

### Notes:

> useState always returns an array with 2 elements.

> When the state function is called, React will execute the component function again and repaint the UI.

> The only argument needed for `useState()` is the initial state (here `props.title`).

> **useState in a nutshell:** You register state with `useState`, you always get back 2 values, the value itself and the updating function. You call the updating function whenever the state should change and you use that first element whenever you want to use the state value for outputting it in the JSX code. React does the rest.
