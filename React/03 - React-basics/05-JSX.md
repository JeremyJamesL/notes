# JSX

JSX code is html code inside of Javascript. It stands for Javascript XML (html is xml you could say):

```js
function App() {
  return (
    <div>
      <h2>Let's get started</h2>
    </div>
  );
}

export default App;
```

Again, this only works thanks to the `npm` scripts running in the background.

## Writing valid code

In React components there is one important rule when returning JSX code:

> You must only have one root element per `return` statement.

e.g:

```js
return (
<div>A div</div>
<div>Another div</div>
)
```

As there are multiple root `<div>` elements, this syntax is invalid. Instead, wrapping all in one root `<div>` is correct:

```js
return (
  <div>
    <div>A div</div>
    <div>Another</div>
  </div>
);
```

## Some JSX rules to abide by:

> 1. We want JSX code to be lean and not put too much logic in it.
> 2. Define variable and functions outside of the returned JSX code block.

## A deeper look at JSX

We have already interacted with one of the dependencies we use in the project, which is the React DOM. In index.js:

```js
ReactDOM.render().
```

We don't need to when using `create-react-app`, but in other applications another React dependency we would use is React itself. In the past this would have to be passed into files like so:

```js
import React as "React";
```

This is because, in reality, whenever we use `JSX` we are actually calling methods on the `React` property.

Our custom components, rendered by React, are essentially the same as calling the `createElement` method on the React property:

```js
return React.createElement(
  "<div>",
  {},
  createReactElement("h2", {}, "let's get started")
);
```

This method takes three arguments:

1. The tag (div)
2. Object of properties (here null)
3. The element itself, here you have to call createReactElement again, so on and so on.

It replaces this:

```js
return (
  <div>
    <h2>Let's get started!</h2>

    <Expenses data={expenses} />
  </div>
);
```
