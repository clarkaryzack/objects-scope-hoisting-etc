## Scope, hoisting and compartmentalization

### Answer the following:
In you own words, explain the concepts of scope, hoisting, compartmentalization.

Scope is a property of variables that makes some global, and some local (specific to a single function.)

Hoisting is a property of JavaScript that causes variable declarations to be moved to the beginning of a function.
Strict mode prevents hoisting.

### Provide examples for all three, below:

#### Scope:

(function(){
  "use strict";

  var x = "I'm a local variable";
  //console.log(y)

  function scopeThis(){
    var y = "I'm a global variable";
    console.log(x);
  }
  scopeThis();
})();

#### Hoisting:

(function(){
  "use strict";

  function warmUp() {
    console.log(x);
    console.log(foo());

    var x = "variable hosting!";

    function foo() {
      return "function hoisting";
    }
  }
  warmUp();
})();

#### Compartmentalization:

(function() {
  "use strict";
  var multiply = 2 * 8;

  function duplicate() {
    let multiply = 2 * 10;
  };

  duplicate();

  console.log( "multiply", multiply );
  console.assert( multiply == 16, "Test failed. How can we isolate duplication()" );
})();
