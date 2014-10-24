# Object.create()
```javascript
function Test(){
	this.myString = 'Hello'
}

var a = new Test();
console.log(a.myString); //Hello

var b = Object.create(Test);
console.log(b.myString);//undefined

var c = Object.create(a);
console.log(c.myString);//Hello
```

Do not confuse ``Object.create()`` with ``new``.  ``Object.create(proto)``  creates a new object using the ``proto`` as the prototype object.

The example above shows how ``var b`` has not got the ``myString`` property because when calling the ``Object.create()`` we gave it a constructor rather then an object to set as the prototype.

However ``var c``  has the property ``myString`` because we gave the ``Object.create`` an object to be used as the prototype.  So when we reference ``myString`` it can traverse up the prototype tree.

Below is an example showing how to achieve the same effect with out the use of ``Object.create()`` and using ``new``.

```javascript

//set up my object to inherit from
function Testprototype(){
  this.myString = 'aTest';
}
var a = new Testprototype();

//create object with a as prototype
var b = Object.create(a);


//equivalent as above with new
function Empty(){
//dummy constructor
}
Empty.prototype = a;
var c = new Empty();

//results
console.log(b);// Testprototype { myString="aTest"}
console.log(c);// Testprototype { myString="aTest"}

```





Read more

[MDN Object.create()][mdn Object Create]

[mdn Object Create]:https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/create
