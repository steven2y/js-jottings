# Variable References

Here is some javascript fun that may catch people out.

```javascript
function Privatevars(){
  var privateVar = 'private var';

  this.publicVar = privateVar;

  this.setPrivateVar = function(theVar){
    privateVar = theVar;
  }
}

var a = new Privatevars();

console.log(a.publicVar); //outputs 'private var'

a.setPrivateVar('public var');

console.log(a.publicVar); //outputs 'private var'

```

So why did `a.publicVar` not change, even after setting the `privateVar`.

Well the problem is similar to the following.

```javascript
var privateVar = 'hello'
var publicVar = privateVar;

console.log(publicVar); //outputs 'hello'
console.log(privateVar);//outputs 'hello'

privateVar = 'world'

console.log(publicVar);//outputs 'hello'
console.log(privateVar);//outputs 'world'
```
The statement `var publicVar = privateVar;` actually assigns the publicVar to a **copy** of the privateVar because a string is a primitive (undefined, null, boolean, string and number).  So changing `privateVar` will not do anything to `publicVar`;


What if we had an object and changed the values inside.
```javascript
var privateVarObject = {text: 'hello'}
var publicVarObject = privateVarObject;

console.log(publicVarObject.text); //outputs 'hello'
console.log(privateVarObject.text);//outputs 'hello'

privateVar.text = 'world'

console.log(publicVarObject.text);//outputs 'world'
console.log(privateVarObject.text);//outputs 'world'
```
The statement `var publicVarObject = privateVarObject;` now actually assigns the `publicVarObject` to point to the **same** object as the `privateVarObject`.  So changing the object attributes will effect both.


Some background reading [Javascript Data Structures ](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures)
