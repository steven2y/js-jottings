# Object Destructuring assignment

So destructuring is just a funky way of extracting data from a data structure.  Here are a couple examples.


``` javascript

//Example 1 Simple

let objTest = { x:1, y: 2 , z: 3}
let {x,y,z} = objTest;

console.log(x); //1
console.log(y); //2
console.log(z); //3

//Example 2 Simple
//another way of object destructuring without declaration
let objTest = { a:9, b: 8 , c: 7}
let a,b,c;

({a,c,b} = objTest); //requires surrounding ()

console.log(a); //9
console.log(b); //8
console.log(c); //7

```

As long as you have the variable name that matches the property you are trying to extract it will be assigned.

``` javascript
//Example 3
let z = {
          a:{
              b:{
                  c:{
                      d:1
                    },
                   e:2
                },
              e:3
             }
        };

let{a:{b:{c:{d}, e}}} = z;

console.log(d); //1
console.log(e); //2

//Example 4
let z = {
          a:{
              b:{
                  c:{
                      d:1
                    },
                   e:2
                },
              e:3
             }
        };

let{a:{b:{c:{d}, e}, e:f}} = z; // note the e:f re-assignment

console.log(d);
console.log(e);
console.log(f);
```
As you can see you can destruct from nested and reassign the variable if you have two variable names the same



```javascript
//Example 5 same variable re-assign
let z = {
          1:{a:'my'},
          2:{a:'big'},
          3:{a:'world'}
        };

let {1:{a:word1}, 2:{a:word2}, 3:{a:word3}} = z;

console.log(word1); //my
console.log(word2); //big
console.log(word3); //world

```

So whats the point of all this, well it means you can do stuff like this.

```javascript
//Example 6 destruct function returns
function doSomething(){
  return {a:1, b:2};
}

let {a,b} = doSomething();

console.log(a); //1
console.log(b); //2
```
So now we can easily extract out variables from large responses alternatively we can destruct it when as we use it in a function, see below.

```javascript
//Example 7 destruct function params
function destructor({a,b,c}){
  console.log(a);
  console.log(b);
  console.log(c);
}

destructor({a:'hello', b:'my', c:'world'});

//output
//hello
//my
//world

//Example 8 in an iterator
var myArray = [
  {a:1,b:2,c:3},
  {a:4,b:5,c:6},
  {a:7,b:8,c:9}
];

myArray.forEach(function({a,b,c}){
  console.log(a,b,c);
});

//output
// 1 2 3
// 4 5 6
// 7 8 9
```

Read more here

[Destructuring assignment][Destructuring assignment]

[Destructuring assignment]:https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Destructuring_assignment




