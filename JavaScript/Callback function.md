A callback function is a function that is passed as an argument to another function and is executed later, usually after some operation is completed.

## Why Use Callbacks?

**To handle asynchronous operations (e.g., reading a file, making an API request).

**To customize behavior in functions (e.g., sorting, filtering).

**To improve code reusability.


```
let myName = 'Prince'

function func2(newName){
   myName = 'Obot'
 }

function func1(middleName, callback){
   console.log(myName)
   callback()
   console.log(myName)
 }
 func1('Samuel', func2)
```