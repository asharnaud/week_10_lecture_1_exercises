### (1) Describe a closure in JavaScript.

An inner function keeps access, by reference, to variables and parameters outside of the immediate lexical scope.

### (2) Returning an inner function does not call the function when the outer function is called. How can this be resolved?

You can return the inner function inside of the outside function.

### (3) In the example below, why does the global variable get reassigned?

var reassignmentExample = "Global variable";

function testAssignment() {
  reassignmentExample = "Local variable";

  console.log(reassignmentExample);     
}

console.log(reassignmentExample); // Logs: Global variable
testAssignment(); // Logs: Local variable
console.log(reassignmentExample); // Logs: Local variable (the global variable is reassigned)

The value of the global variable was changed inside of the function. Then that function was called so that is what changed the variable.

### (4) When would it be necessary to store the value of this in a variable?
In order to obtain the invocation context of the outer function using this, it needs to be stored in a variable in the scope of the inner function.

### (5) Describe the difference between function scoping and block scoping.
In function scoping, any variables declared within a function are visible anywhere within that same function. In block scope, a variable confined in a block of code is only visible inside that block of code.

### (6) In this example, why does logging 'hoistedVar' return 'undefined'?

function hoistingExample() {
  console.log(hoistedVar);
  var hoistedVar = "Hoist me!";
}

Hoisting does not work on variables when it is inside of the function so you can not call it before you define it. 
