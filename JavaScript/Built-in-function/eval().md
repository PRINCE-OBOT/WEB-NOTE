eval() takes a string of JavaScript code and runs it as if it were part of your program.

Example 1: Basic Arithmetic

`const expression = "2 + 3 * 4";
`console.log(eval(expression)); // Output: 14`

### Injecting eval
` function test() {
  let isAdmin = false;
 ` const userInput = 'isAdmin = true;
  `eval(userInput); // Dangerous! Changes isAdmin
  `console.log(isAdmin); // Output: true
}
test();`

### Direct and Indirect eval()

1. Direct eval : `eval()` modifies variable in both local scope (local scope can be inside a function) and global scope.

**Syntax**
`let myName = 'Prince';
 `eval('myName = "Obot"')
 `console.log(myName)`

2. Indirect eval : This does not modify the variable, instead, execute the expression. 

**Syntax**
 ` function func(arr){
`` return eval(arr)
  }
 `let num = '3 + 8'
 `console.log(func(num))`

**Without function**
`let obj = '2 + 8'
`console.log(eval(obj))`

### By default eval operate with variable in global scope, but it inside a local scope, it first checks to see if the variable to be modify or executed is there before advancing to the global scope-fair enough - you can still `Explicitly` set eval to operate only in it global scope. Using the syntax, below.

`(0, eval)` modifies variable within global scope only, i.e, it cannot modify variable when it is inside a function, or local scope.

`let localVar = 4
function test() {
  let localVar = 5;
(0, eval)('localVar = 10;'); // Changes `localVar` globally, not locally.
  console.log(localVar)
   // Outputs: 5
}
test();
console.log(localVar) // 10`

*The example above update the value of the global scope with checking the local scope.*

``let localVar = 4
function test() {
  let localVar = 5;
eval('localVar = 10;'); // Changes `localVar` globally, not locally.
  console.log(localVar)
   // Outputs: 10
}
test();
console.log(localVar) // 4`

*The code above update the value of the local scope, since it is not explicitly specified, because it checks the local scope first before advancing to the global scope.*

### Why use strict mode
Incase where an `undeclared variable` can be assigned a value, is aborted 

Example :
`myName` has not be declared using, either: let, const or bar but it eval() makes it behave as if it has be declared.
This is why you need strict mode.

`eval('myName = "Prince"')
`console.log(myName)`// 'Prince'

*If strict mode is activated*

`"use strict"
`eval('myName = "Prince"')
`console.log(myName) //myName is not defined