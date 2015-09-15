# Freeze & Seal

So freeze and seal are similar but slightly different.  Freeze makes the object immutable where as seal only locks down the propertieson the object, the values themselves can still be altered.

Example of seal

```javascript
let obj = {
  a: 'funky',
  b: 'object'
};

obj.c = 'stuff'; //normally you can add prop

let sealedObj = Object.seal(obj);

sealedObj === obj //true

sealedObj.d = 'more';
obj.e = 'and more';

obj;//still {a: 'funky', b: 'object', c: 'stuff'}

sealedObj.a = 'updated'; //can still update existing values

obj;//still {a: 'updated', b: 'object', c: 'stuff'}

```

Example of freeze

```javascript
let obj = {
  a: 'funky',
  b: 'object',
  c: {
    a:'innerFunky'
  }
};


let frozenObj = Object.freeze(obj);

frozenObj.a = 'hunky'; //try update

frozenObj.d = 'more'; //try adding

obj.e = 'and more'; //tryadding to original object

obj;//no change {a: 'funky', b: 'object', c: {a:'innerFunky'}}

frozenObj;//no change {a: 'funky', b: 'object', c: {a:'innerFunky'}}


frozenObj.c.a = 'innerObject';//however

obj;//inner object updated  {a: 'funky', b: 'object', c: {a:'innerObject'}}

```

So both examples we can see the object been locked down so you can not add or remove properties on the object.  However for sealed object you can update the values.

One exception, as seen from the freeze example, is that the seal and freeze methos is shallow. So any inner nested/inner objects reference by the properties can still be edited.

For more reading see:

[MDN Object.seal()][mdn Object.seal()]

[MDN Object.freeze()][mdn Object.freeze()]


[mdn Object.freeze()]:https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/freeze

[mdn Object.seal()]:https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/seal

