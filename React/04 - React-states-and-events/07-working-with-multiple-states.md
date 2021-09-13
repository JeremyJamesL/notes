# 07 - Working with multiple states

You can have more than one state per component, they are completely separate from one another:

```js
const ExpenseForm = () => {
  const [enteredTitle, setEnteredTitle] = useState("");
  const [enteredAmount, setEnteredAmount] = useState("");
  const [enteredDate, setEnteredDate] = useState("");

  const titleChangeHandler = (event) => {
    setEnteredTitle(event.target.value);
  };

  const amountChangeHandler = (event) => {
    setEnteredAmount(event.target.value);
  };

  const dateChangeHandler = (event) => {
    setEnteredDate(event.target.value);
  };

  return (
    <form>
      <div className="new-expense__controls">
        <div className="new-expense__control">
          <label>Title</label>
          <input type="text" onChange={titleChangeHandler} />
        </div>
      </div>
      <div className="new-expense__controls">
        <div className="new-expense__control">
          <label>Amount</label>
          <input
            type="number"
            min="0.01"
            step="0.01"
            onChange={amountChangeHandler}
          />
        </div>
      </div>
      <div className="new-expense__controls">
        <div className="new-expense__control">
          <label>Date</label>
          <input
            type="date"
            min="2019-01-01"
            max="2020-12-31"
            onChange={dateChangeHandler}
          />
        </div>
      </div>
      <div className="new-expense__actions">
        <button type="submit">Add Expense</button>
      </div>
    </form>
  );
};
```

1. Multiple states per component is totally fine.
2. The states are separate from one another.
3. We call them state 'slices'

## The alternative approach

Instead of multiple state slices, there is a way to unify states.

For our example above, as all of the state changes are on the form, and are basically doing the same thing, we are repeating ourselves.

So, instead we can go for one state by using an object as the state argument:

```js
const [userInput, setUserInput] = useState({
  enteredTitle: "",
  enteredAmount: "",
  enteredDate: "",
});

const titleChangeHandler = (event) => {
  setUserInput({
    ...userInput,
    enteredTitle: event.target.value,
  });
};

const dateChangeHandler = (event) => {
  setUserInput({
    ...userInput,
    enteredDate: event.target.value,
  });
};

const amountChangeHandler = (event) => {
  setUserInput({
    ...userInput,
    enteredAmount: event.target.value,
  });
};
```

In this example, we store our states in an object and then pass that object as the setUserInput argument, using destructuring to retain the values of the non-relevant value. This retains the key value pairs without discarding them.
