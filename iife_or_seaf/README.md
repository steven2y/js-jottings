# IIFE or SEAF
Immediately-Invoked Function Expression or
Self-Executing Anonymous Functions

So these are just anonymous functions that execute immediately.

```javascript
//Example 1
(function(){
    console.log('Hello');
})()
//Example 2
//same as
(function(){
    console.log('Hello');
}())

//Example 3
//this does not work, fails with SyntaxError: function statement requires a name
function(){
    console.log('Hello');
}()

//Example 4
//this fails with SyntaxError: syntax error
function test(){
    console.log('Hello');
}()

```

Example 3 did not work because the parser thinks you are trying to define a function which does not have a name so it fails. Example 4 has a name but that fails as well, because a function definition is a statement and the trailing ```()``` that is suppose to invoke the function acts just as a grouper.

The ```( )``` that surrounds the function makes the parser parse the function as an expresssion and so allows it to be executed.

##Whats the point?
Since Javascript only has function scoping and closures, this is a very useful pattern for encapsulating modules and making sure your namespace is not polluted with unwanted variables.

```javascript
var timer = (function(){
  var count = 1;

  return {
    tick: function(){
      console.log(count++);
    }
   };

})()

timer.tick();// 1
timer.tick();// 2
timer.tick();// 3

console.log(timer);// Object { tick=function()}
console.log(count);//ReferenceError: count is not defined

```
Here the anonymous function returns an object that has a function that references a variable with in the anonymous function.  As you can see the ```count``` is not accessible from outside the function.




More reading here

http://benalman.com/news/2010/11/immediately-invoked-function-expression/
