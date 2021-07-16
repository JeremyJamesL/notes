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
