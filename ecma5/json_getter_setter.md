# JSON getter setter

Avaliable from ECMAScript 5.1.

Example of getter being set on an object.
```javascript
var testObj = {
  someText: 'Hello'
}

var objWithGetter = {
  testString: 'Yo',

  testFunc: function(){
    return this.testString + 'Yo';
  },

  get yoYo() {
    return this.testFunc() + this.testFunc();
  },

  get helloWorld() {
    return testObj.someText + ' World'
  }
}

console.log (objWithGetter.helloWorld); // Will return "Hello World".
console.log (objWithGetter.yoYo); // Will return "YoYoYoYo".
```

So far only tried in FireFox and Chrome

For more reading see:

[MDN getter][mdn getter]

[MDN setter][mdn setter]

[mdn getter]:https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/get#Specifications
[mdn setter]:https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/set
