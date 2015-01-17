 # Object defineProperty()
Avaliable from ECMAScript 5.1.


```javascript
var testObj = {a : 'hello'};


//same as testObj.b = 'hello b'
// except
// you cannot enum it
// you cannot config
// you cannot write
Object.defineProperty(testObj, 'b',{
  value:'hello b'
  //other options available
  //enumerable //default false
  //writable // default false
  //configurable //default false

  //optional
  //set : function()
  //get : function()
});

console.log(testObj.a);//outputs 'hello'
console.log(testObj.b);//outputs 'hello b'

//try to write but cannot
testObj.b = 'new b'
console.log(testObj.b);// ouputs 'hello b'

//try to enum  but cannot see
for(x in testObj){
  console.log(x);
};//only outputs a

//cannot config i.e. not deletable
delete testObj.a;
delete testObj.b;

console.log(testObj.a);// undefined
console.log(testObj.b);// ouputs 'hello b'
```


So Object.defineProperty is a very useful method that can modify a given object giving you control over the properties of the object.  You can additional set `getter`'s and `setter`'s.

Watch out for the difference between `configuarable` and `writable`.  One is deletable and changable the later is only changeable with an assignement operator.


For more reading see:

[MDN Object.defineProperty()][mdn Object.defineProperty()]

[mdn Object.defineProperty()]:https://developer.mozilla.org/en/docs/Web/JavaScript/Reference/Global_Objects/Object/defineProperty

