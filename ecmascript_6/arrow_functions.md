# Arrow Functions

So arrow functions are functions defined with a fat arrow. Example
```javascript
var sumFunc = (a,b) => a+b;
sumFunc(2,9)// output 11
```

So the above is the same as
```javascript
var sumFunc = function(a, b){
    return a+b;
}
sumFunc(2,9)// output 11
```

##Shorter function declaration##
So we have a shorter way of declaring a function.  Which is useful for anonymous functions etc..

```javascript
var testData = [1,2,3,4,5,6,7,8];
console.log(testData.map( n => n*2));
//same as
console.log(testData.map(function(num){return num*2;}));
```

##Lexical this##

Arrow functions capture the value of ```this``` from the enclosing context, so you should not need to bind or manage ```this``` as much.
```javascript
var testObj = {
  data: [1,2,3,4,5,6,7,8],

  multiplier: 2,

  //calc with this management
  calc: function(){
    return this.data.map(function(num){
      return num*this.multiplier;
    }, this);
  },

  //calc with arrow function
  calcArrow: function(){
    return this.data.map( n => n*this.multiplier);
  }
}
```


For more reading see:

[Arrow Functions][Arrow Functions]

[Arrow Functions]:https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions
