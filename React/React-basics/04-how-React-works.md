# How React works

React is about writing declarative code, vs imperative code.

Vanilla JS is **imperative**, in that the code must be explicit and authoritive in what it wants to do, i.e, defining and adding elements to a page:

```js
const paragraph = document.createElement("p");
para.textContent = "This is visible";
document.getElementById("root").append(para);
```

This code defines and element and then explicitly dictates where the element should go. Clear, step-by-step instructions.

React, is **declarative**, in that the code doesn't specify an exact procedure to follow. You create a desired end state, for instance in JSX, and then let React do the remainder of the work in dictacting where in the DOM the element will go:

```js
function App() {
  return (
    <div>
      <h2>This is the end state</h2>
    </div>
  );
}
ReactDOM.render(<App />, document.getElementById("root"));
```
