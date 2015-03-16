# Let
WIP

Example

```javascript
for (var i = 0  ; i<=10 ; i++){
  setTimeout(function(){
    console.log(i); //display 6 10 times
  }, i*1000);
}
```

First attempt to fix
```javascript
for (var i = 0  ; i<=10 ; i++){
  var a = i;
  setTimeout(function(){
    console.log(a);//display 6 10 times
  }, a*1000);
}
```

Maybe use scope variable fixing
```javascript
for (var i = 0  ; i<=10 ; i++){
  (function(i) {
    setTimeout(function(){
      console.log(i);
    }, i*1000);
  })(i);
}
```
This works but bit verbose;

How about a ```let```
```javascript
for (var i = 0  ; i<=10 ; i++){
  let a = i;
  setTimeout(function(){
    console.log(a);
  }, a*1000);
}
```
This works as we are block scoping the var ```a```;
