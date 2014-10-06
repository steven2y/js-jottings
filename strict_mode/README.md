# Strict Mode


```strict mode``` is a way to opt in to a restricted variant of JavaScript, this was introduced in ECMAscript 5.  To use ```strict mode``` just place ```'use strict';``` before any statements or with in a function.

Some Key Changes

1. Makes debugging easier by highlighting/throwing errors for common mistakes/typos.

2. Prevents accidental globals.
```javascript
                            // Assuming a global variable mistypedVariable exists
mistypedVaraible = 17;   // this line throws a ReferenceError due to the
                            // mispelling of variable
```

3. Throws error deletion of undeletable properties.
```javascript
"use strict";
delete Object.prototype; // throws a TypeError
```

4. Disallows duplicate property names or parameter values.
```javascript
"use strict";
//property name
var o = { p: 1, p: 2 }; // !!! syntax error
//Parameter name
function sum(a, a, c){ // !!! syntax error
    "use strict";
     return a + b + c; // wrong if this code ran
}
```

5. Makes eval() safer.  Variables and functions declared inside of an eval() statement are not created in the containing scope, strict mode also  forbids deleting plain names.
```javascript
"use strict";
eval("var x; delete x;"); // !!! syntax error
```


For more reading see:

[MDN Strict Mode][Mdn Strict Mode]

[MDN Strict Mode Transition][Mdn Strict Mode Transition]


[Mdn Strict Mode]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Strict_mode
[Mdn Strict Mode Transition]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Strict_mode/Transitioning_to_strict_mode
