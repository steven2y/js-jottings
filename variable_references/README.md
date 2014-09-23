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

