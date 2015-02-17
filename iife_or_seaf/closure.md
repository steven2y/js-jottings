# Closure
```javascript
var a = [];

for(var i = 0; i<3 ;i++){
  a[i] = function(){
    console.log(i);
  }
}

a[0](); //3
a[1](); //3
a[2](); //3
```


Ok we are seeing '3' being outputted because of the lexical scoping of functions.
