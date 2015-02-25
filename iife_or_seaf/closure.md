# Closures
```javascript
var a = [];

for(var i = 0; i<3 ;i++){
  console.log(i);//will output 0,1,2
  a[i] = function(){
    console.log(i);
  }
}

a[0](); //3
a[1](); //3
a[2](); //3
```


OMG what is going on here, well we are seeing '3' being outputted because of the lexical scoping of functions.  Here the functions when executed will look at its current scope for variable 'i', not find it and then look at the parent scope.  In this case it's the 'i' inside the for loop, which has already been incremented to '3'.

So how do we fix this? Well there are couple solutions.

```javascript
var a = [];
var createFunc = function(lockedNumber){
    return function(){
        console.log(lockedNumber);
    };
};

for(var i = 0; i<3 ;i++){
  a[i] = createFunc(i);
}

a[0](); //0
a[1](); //1
a[2](); //2
```

So how come the function `a[0]()` returns `0` and `a[1]()` returns `1`?  The `createFunc` function returns a function and a closure is linked to this function of the context of when it was created.  So in this case `a[0]()` will return `0` because at the time of creation the `lockedNumber` variable was set to `0` and for `a[1]()` it was '1'.


The following will also do the same but using a IIFE
```javascript
var a = [];

for(var i = 0; i<3 ;i++){
  a[i] = (function(lockedNumber){
    return function(){
        console.log(lockedNumber);
    };
  })(i)
}

a[0](); //0
a[1](); //1
a[2](); //2
```

For more reading see:

[MDN Closures][mdn closures]
[mdn closures]:https://developer.mozilla.org/en-US/docs/Web/JavaScript/Closures

