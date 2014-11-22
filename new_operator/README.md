# New Operator

The `new` operator is used to make an instance of an object.  Below is a number of ways of making an object.

```js
var AClass = TheClass; //function expression

function TheClass(){//defined function constructor
  //constructor
  this.val = 'world';
  return {};
}

console.log(AClass()); // running it as just a function Object {}
console.log(TheClass()); // running it as just a function Object {}

var obj1 = new AClass(); //instance of object
var obj2 = new TheClass(); //instance of object
var obj3 = new TheClass; //instance of object same as new TheClass()

console.log(obj1);//  Object {}
console.log(obj2);//  Object {}
console.log(obj3);//  Object {}
```

So how come they all outputted an `Object{}`?  Well the first few console logs actually just called the constructor as a normal function and just outputted the return value which is `return {};`.

However `obj1, obj2, obj3` also outputted `Object{}`.  This is because the **object** returned by the constructor function becomes the result of the `new` expression.  Note its an **object** that is returned, so if I was to return a **string** I would get a different result, as follows.

```js

var AClass = TheClass;//function expression

function TheClass(){//defined function constructor
  this.val = 'world';
  return 'hello';//a string
}


console.log(AClass()); //prints 'hello'
console.log(TheClass()); //prints 'hello'

var obj1 = new AClass();//instance of object
var obj2 = new TheClass();//instance of object
var obj3 = new TheClass;//instance of object same as new TheClass()

console.log(obj1);// TheClass { val="world"}
console.log(obj2);// TheClass { val="world"}
console.log(obj3);// TheClass { val="world"}
```

Read up on it here.

[Javascript new operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/new)
