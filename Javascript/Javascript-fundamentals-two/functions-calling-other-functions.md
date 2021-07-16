# Calling functions from inside another function


```javascript
function cutFruitPieces(fruit) {
    return fruit * 4;
}

function foodProcessor(apples, oranges) {
    const applePieces = cutFruitPieces(apples);
    const orangePieces = cutFruitPieces(oranges);
    const juice = `Juice with ${applePieces} apples and ${orangePieces} oranges.`;
    return juice;
}

console.log(foodProcessor(2, 3));
```

* It's very common for one function to call another function
* It helps to achieve the D.R.Y (don't repeat yourself) principle and to organise code effectively. 
* 