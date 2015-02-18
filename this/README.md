# this

Prototypical inheritance example.  Just showing that context of 'this' changes.


```javascript

//simple constructor
function Testa(a,b,c){
  this.a = a;
  this.b = b;
  this.c = c;
}

//add a prototype function to Testa
Testa.prototype.blurb = function(){
  return console.log(this.a,this.b,this.c);
}

//another constructor that 'inherits' from Testa
function Testb(a,b,c,d,e){
  this.d = d;
  this.e = e;

  //call the TestA as a function but giving 'this' as the context
  //so you are effectively assigning the a,b,c to 'this' TestB object
  Testa.call(this, a,b,c);
}

//setup your prototype chain
Testb.prototype = new Testa(); //could do Testb.prototype = Object.create(Testa.prototype); creates a new object with the 'Testa.prototype' as the prototype
Testb.prototype.constructor = Testb; //see reference below


var objectB = new Testb(1,2,3,4,5);
console.log(objectB); //
console.log(objectB instanceof Testb,' instance of TestB'); // true instance of TestB
console.log(objectB instanceof Testa, ' instance of TestA'); // true instance of TestA
console.log(typeof objectB, 'typeOf'); //object typeOf

objectB.blurb();//1,2,3 which is the a,b,c from the testB object
```




For more reading see:

[Prototype Constructor][Prototype Constructor]

[Instance Of][Instance Of]

[Prototype Constructor]:https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/constructor

[Instance Of]:https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/instanceof
