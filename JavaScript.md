
## Datatype
**Null** this is a datatype that represent nothing but when use in a mathematical expression becomes 1.
`null * 4 = 0`
`null = object`
`null ** NaN = NaN`
`null ** String = NaN`
`null * NaN = NaN`
`null ** undefined = 1`
`null * undefined = 0`

## String methods
**split** : it is use to extract data from a string using it `separator`  converting it into an array. 

Example: 
`const myName = "Prince"
  let splitName = myName.split("") //output ["P", "r", "i", "n", "c", "e"]
  The split method split the string using "" separator and return the output in array. 
  
  myName.split("")[0]
  console.log(splitName) // output ["P"] `
  
The split method split the string using "" separator and return the array index [0]


## functions
**Array inside a function** 

`function greet(fullName, [firstName, lastName]) {
    console.log(`${fullName} ${firstName} ${lastName}`);
}
greet("Prince Obot", ["Prince", "Obot"]);
`
**Object inside a function**
`function greet(fullName, {firstName, lastName}) {
    console.log(`${fullName} ${firstName} ${lastName}`);
}
greet("Prince Obot", {firstName: "Prince", lastName :"Obot"});
`
*Note*: do not omit the square bracket or curly bracket when calling the function, else it prompt an error. alternative if you want to omit it.

`function greet(fullName, {firstName, lastName} = {firstName:"Prince"}, lastName: "Obot") {
    console.log(`${fullName} ${firstName} ${lastName}`);
}
greet("Prince Obot");

## Setting the prettier to function in only javascript
`
{
  "files.autoSave": "afterDelay",
  "liveServer.settings.donotShowInfoMsg": true,
  "editor.defaultFormatter": "esbenp.prettier-vscode",
  "[javascript]":{
    "editor.formatOnSave": true,
  },
  "editor.formatOnPaste": true,
  "liveServer.settings.CustomBrowser": "microsoft-edge"
}

`
## Usage of console.log and return
Use return when you want to reuse the specific code in the program.
use console when you want to display the output.

## new Map
map are use in place of object when you don't want your code to rely on just retrieving information with just string as it is in object.

**map parameters**
**key** : it does not rely on string unlike object, it can be literal anything, it is use to get the map value
**value**: it is the value assign to the key.

**inbuilt map method**
get, size, has, set, delete, clear

**get** it is use to extract a part of the map that meets it conditions
`
const map = new Map([
  [user, "A"],
  [2, "B"],
  [3, "C"],
  [4, "D"],
]);

console.log(map.get(2)) // output: B
`
**has** it return true or false. it an map variable has it key.
`
const map = new Map([
  [user, "A"],
  [2, "B"],
  [3, "C"],
  [4, "D"],
]);

console.log(map.has(2)) // output: true
`

**size** it is use to check the length of the map

`const map = new Map([
  [user, "A"],
  [2, "B"],
  [3, "C"],
  [4, "D"],
]);

console.log(map.size) // output: 4
`

**set** it is use in appending or adding more map.
`const map = new Map([
  [user, "A"],
  [2, "B"],
  [3, "C"],
  [4, "D"],
]);
map.set(4, "E")
console.log(map.size) // output: 5
`
**delete** it is use to delete a map.
`const map = new Map([
  [user, "A"],
  [2, "B"],
  [3, "C"],
  [4, "D"],
]);

map.delete(user)
console.log(map) // output: 
[2, "B"]
[3, "C"]
[4, "D"]
`
**clear** is use to remove the entire map
`const map = new Map([
  [user, "A"],
  [2, "B"],
  [3, "C"],
  [4, "D"],
]);
map.clear()
console.log(map) // map(no entries)
`
**using forEach**
`const user = {
    name : "kyle",
    spec : 45
}
const map = new Map([
  [user, "A"],
  [2, "B"],
  [3, "C"],
  [4, "D"],
]);

map.forEach((value, key) =>{
    if(key > 2)console.log(value)
})`

### Destructuring, spread operator and rest operator

This `spread` and `rest` operator have the same syntax but serve distinct purpose in application.

**Spread** : it takes an array, object or values that are iterable and return the content of it individual.

*Using string*
` const val = "57";
 const checkVal = [...val, 7]
 console.log(checkVal) // ["5", "7", 7]`

*Using array* 
`const val = [23, 45];
 let checkVal = [...val, 7]
 console.log(checkVal) // [23, 45, 7]
 `
*Using object*
`const val = {name:"Prince", age:30};
 let checkVal = [{...val}, 7]
 console.log(checkVal) // [{name:"Prince", age:30}, 7]`

**Rest** 
It's a way of saying the rest of them(I can't manually begin to type each element or values).

*Easily identify `rest` from `spread`: `rest` always return a new variable 

*Usage in Destructuring 

` const largeInfo = ["Prince", "Samuel", "Obot", "Alexander"]
 let [indexOne, ...restOfValue] = largeInfo
 console.log(indexOne) // "Prince"
 console.log(restOfValue) // ["Samuel", "Obot", "Alexander"]`

The variable `restOfVariable` is a new variable that holds the rest of the variable.

*In the example for `rest` above, the regular variable is define first before including the `rest` method. this is to say that `rest` method always appears at the last.*

*Usage in function *

`function checkRestOperator(numb1, ...arr){
  for(i=0; i<arr.length;i++){
  if(numb1 > arr[i]){
    console.log(arr[i])
  }
  }
}
checkRestOperator(1, 3, 7, 8, 0)`

**Destructuring**: it is essentially use for extracting values from object or array.

*Usage in Array*

`const colors = ["Red", "Blue", "Yellow"]
const [,colorBlue] = colors
console.log(colorBlue) // "Blue"

*the element blue was extracted from the array*`

*Usage in object *

`const colors = {firstColor: "Red", secondColor: "Blue", third:"Yellow"}
const {secondColor} = colors
console.log(secondColor)`

*Usage in nested array*

` [{ name: 'Alice', skills: ['JS', 'React'], address: { city: 'NY' } },
    { name: 'Bob', skills: ['Python', 'ML'], address: { city: 'SF' } },
    { name: 'Charlie', skills: ['HTML', 'CSS'], address: { city: 'Chicago' } }]
];
//Goal: is to append `favouriteColor : "Yellow" in the first array index i.e data[0].

//learning how to append element or values with destruction, rest or spread?

//1. check the container type of bracket, if its an array or object.

//In this case we have an array followed immediately by an object. so what to do? make sure to destructure the array first, so as to provide the information of the index to be edited.
const [indexOne, ...restOfArr] = data // the index one of data has been extracted also known as destructuring. secondly: instead of manually declaring each variable for each element index, i use the rest operator.
let appendingInfo =[
  {...indexOne, favouriteColor : "Yellow"}, restOfArr
  ]
  console.log(appendingInfo)
  
  //...indexOne arrange like `name: 'Alice', skills: ['JS', 'React'], address: { city: 'NY' }, favouriteColor : "Yellow" ` and then enclosed in an object.`
  
*Usage in  nested object*

`const data = [
    { name: 'Alice', skills: ['JS', 'React'], address: { city: 'NY' } },
    { name: 'Bob', skills: ['Python', 'ML'], address: { city: 'SF' } },
    { name: 'Charlie', skills: ['HTML', 'CSS'], address: { city: 'Chicago' } }
];
//Goal: is to append `Grid` in the first array index i.e data[0].skills array.

//learning how to append element or values with destruction, rest or spread?

//1. check the container type of bracket, if its tgat if an array or object.

//In this cade we have an array follow immediately by an object. so what to do? make sure to destructure the array first.
const [indexOne, ...restOfArr] = data // the index one of data has been extracted also known as destructuring. secondly: instead of nanually declaring each variable for each element index, i use the rest operator.
let appendingInfo =[
  {...indexOne, skills:[...indexOne.skills, "Grid"]}, restOfArr
  ]
  console.log(appendingInfo)
  
  //...indexOne arrange like `name: 'Alice', skills: ['JS', 'React'], address: { city: 'NY' }, favouriteColor : "Yellow" ` and then enclosed in an object.`

*General usage in nested array and object*

`const data = [
    { name: 'Alice', skills: ['JS', 'React'], address: { city: 'NY' } },
    { name: 'Bob', skills: ['Python', 'ML'], address: { city: 'SF' } },
    { name: 'Charlie', skills: ['HTML', 'CSS'], address: { city: 'Chicago' } }
];
//Goal: is to append `Grid` in the first array index i.e data[0].skills array.

//learning how to append element or values with destruction, rest or spread?

//1. check the container type of bracket, if its an array or object.

//In this case we have an array follow immediately by an object. so what to do? make sure to destructure the array first.
const [indexOne, ...restOfArr] = data // the index one data has been extracted also known as destructuring. secondly: instead of manually declaring each variable for each element index, i use the rest operator.
let appendingInfo =[
  {...indexOne, skills:[...indexOne.skills, "Grid"]}, restOfArr
  ]
  console.log(appendingInfo)
  
  //...indexOne arrange like `name: 'Alice', skills: ['JS', 'React'], address: { city: 'NY' }, favouriteColor : "Yellow" ` and then enclosed in an object.`

*Note :* Use array destruction for array and object Destructuring for object.

### Pure Function 
It's simply a function with it own rules.
1. Do not use the a variable outside of the pure function scope - `side effects`- as if the variable value is changed it affects the function making it impure.

2.  Do not directly modify an array or object - `immutability` - as directly modify the array or object outside of its scope, makes it impure. *So what to do?* If you want to use an array or object, you create a duplicate.
Example: `
`const arr = [1, 2, 3];
   function pureFunc(myArr){ const [...rest] = myArr
   return [...rest, 4]
   }
   console.log(pureFunc(arr))
   console.log(arr)`

3. For the same input the output must be the same - `Deterministic` - 

   Example: `const arr = [1, 2, 3];
   function pureFunc(myArr){ return [...myArr, 4]
   }
   console.log(pureFunc(arr))`

### Recursion
It's all about function calling it self over and over again.

Example
`function runRecursive(num){
if(num <= 0) return 0

return num x runRecursive (num - 1)
}
console.log(runRecursive (3))
`
HOW THE CODE RUNS
The initial function is been called and passes the argument 3 to the function.
`function runRecursive(num){`

The argument value is then checked if it is lesser than 0 in other to return.
`if(num <= 0) return 0`
Since it is false, i.e the argument 3 is not lesser than 0, it move to the next line

`return num + runRecursive (num - 1)`

The initial function call seeing a recursion then have to be pause and placed on the call stack.
example 

**Call stack list**
`runRecursive(3)
runRecursive (2)
runRecursive(1)
runRecursive (0)`

The recursion begins
runRecursive (num - 1) = 2.
The value of `num` is 2

The condition is check if 2 is less than 0, which is false, so it runs the code until it get to the recursion line again and now (num - 1) = 1.
The value of `num` is 1

The condition is checked if 1 is less than 0, which is false, then it continues until it get to the recursion lines. 
runRecursive (num - 1) = 0
The value of `num` is 1.

The condition is checked is num is less than equal 0, which is true, then it returns 0 to 0 in the call stack. 
Setting `runRecursive(0)` value to 0

This line is now executed 
`num + runRecursive (num -1)`
In our call stack tree, the recent recursion value is 0, and the `num` value is 1. Which `1 + 0`
Which is equal 1.
The value 1 is then return to the rest of the callstack.
Meaning the `num` duty ends here, 

So the num
Is basically there to help perform the first operation and specify the operator to use when unwinding the function

When the value is been returned to the recent stack it then becomes, 
`1 + 1` = 2
The results it then added to the last recent callstack 
`2 + 2` = 4
And so on
`4 + 3` = 7

Done
As the call stack empties, then `7` it is returned to the initial function and displayed with the console.

### for loop
shorthand for running infinity loop.
`for(;;) 
`{let myName = prompt('Enter my name')
`` if(myName === "Prince")break;
`}`

## String()
It convert everything it contains into a string.

Example:
`const arr = [12, 34]
`String(arr) // 12, 34`

Except it inability to see through object.

`const obj = {name : "Prince"}
`String(arr) // [object, object]`

Inorder to see through the content of object, use.

`JSON.stringify(obj)` // {name : "Prince" }