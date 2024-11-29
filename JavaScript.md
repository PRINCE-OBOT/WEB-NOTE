## Datatype
**Null** this is a datatype that represent nothing but when use in a mathematical expression becomes 1.
`null * 4 = 0`
`null = object`
`null ** NaN = NaN`
`null ** String = NaN`
`null * NaN = NaN`
`null ** undefined = 1`
`null * undefined = 0`

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

## Map
map are use in place of object when you don't want your code to rely on just retrieving information with just string as in object.

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

