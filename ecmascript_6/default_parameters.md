# Default Parameters

Here is a simple example of default parameters using standard function definition and arrow functions.

```javascript
function defaultParams( a = 1, b = 2){
    return a+b;
}

console.log(defaultParams()); //3
console.log(defaultParams(2)); //4
console.log(defaultParams(2,3)); //5

var funcArrow = (c=3,d=4) => c+d

console.log(funcArrow()); //7
console.log(funcArrow(5)); //9
console.log(funcArrow(5,6)); //11
```

So default params are pretty straight forward.  However defaultParams are also available to default params that follow.

```javascript

function defaultParams( a = 1, b = a*2) {
    return a+b;
}

console.log(defaultParams()) //3
console.log(defaultParams(2)) //6
console.log(defaultParams(3)) //9
console.log(defaultParams(1,4)) //5
```

Also the default params are evalutaed at call time so you can do something like.
```javascript
function myParam() {
    return 5
}

function defaultParams(a = myParam(), b = a*2) {
    return a+b;
}

console.log(defaultParams()) //15

```
So as you can see you can do some funky stuff if you really want to.

For more reading see:

[Default parameters][Default parameters]

[Default parameters]:https://developer.mozilla.org/en/docs/Web/JavaScript/Reference/Functions/default_parameters


