# useState - in-depth look

State is a key concept in react.

To clarify:

1. User registers a state for the component in which it is being called.
2. Each component, whether the same, receives its own state. It's a per component instance basis, even if the same component is used more than once: e.g:

```JSX
const [title, setTitle] = useState(props.title);

function clickHandler() {
    setTitle("i've changed");
}


return (
    <Card>
        <button onClick={clickHandler}></button>
    <Card/>
)

```

And the custom component is used 4 times:

```JSX
<Card /> // Click occurs here so change occurs here
<Card /> // No change here
<Card /> // No change here
<Card /> // No change here
```

The change will only occur on the instance of the Card where the button click occurs.

> State is separated on a per-component instance basis.

3. Note that when we use `const` for `useState`, we aren't using it for the variable `props.title`, but instead to register the state. The actual variable `props.title` change is handled elsewhere by React. So we aren't changing a constant here, which is not possible in JS.

4. State initilisation happens only the first time `useState` is used. React stores that `useState` has been initialised on a component, and won't re-initialise it for us. It will instead detect that it has been initialised in the past and will instead grab the latest state and give us that state.
