# 4.6: Getting user inputs

We're going to explore how we get user data in JS

## Getting input values

We have already noted how we can pass event listeners to html elements in React by passing a `prop` and pointing it at a function. Let's do the same for a user input:

```JSX
const titleChangeHandler = () => {
    console.log('do something')
}

return (
    <div class="input-area">
        <input type="text" onChange={titleChangeHandler}>
    </div>
)
```

To get the user input value, we have access to the same default `event` property that we do in Vanilla JS, which we can pass to the event handler function:

```JSX
const titleChangeHandler = (event) => {
    console.log(event.target.value);
}

return (
    <div class="input-area">
        <input type="text" onChange={titleChangeHandler}>
    </div>
)
```
