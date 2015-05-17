# Rest Parameters

The rest parameters is similar to the arguments object.  Where the arguments object is an array **like** object that represent all the arguments given to a function. The rest parameter syntax is used to define an indefinite number of arguments as an array.


Example

```javascript
function restArgsFunc( a, b, ...theRest){
  console.log(a); //aVar
  console.log(b); //bVar
  console.log(theRest); //[1,2,3,4,5,6]
}

restArgsFunc('aVar', 'bVar', 1, 2, 3, 4, 5, 6);
```

The `...theRest` var collects the arguments from that point onwards.  In this case from the third argument. Note the `...` prefix is used to represent the rest parameters.

The rest parameter is also an instance of Array therefore unlike the arguments object it does not need to be spliced into an array.

See below for more examples.

[Rest parameters][Rest parameters]

[Rest parameters]:https://developer.mozilla.org/en/docs/Web/JavaScript/Reference/Functions/rest_parameters
