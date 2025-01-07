### Ways of declaring object 
1. Object Literals : it is used when you don't have to store multiple data.
2. Object Constructors : is more dynamic when you have to store multiple data.
### object
**Creating an empty object can be done using either ways.**
`let user = new Object({}); // "object constructor" syntax 
`let user = {};  // "object literal" syntax
`
**Adding to an object**
`user.name = "Prince"`

**Deleting from an object**
`delete user.name

**Accessing object with multi -words**
`let user = {
  name: "John",
  age: 30,
  "likes birds": true  // multiword property name must be quoted
};

### object Computed properties 
Is when you don't explicitly assign key to a values in objects.

Example: in this example the `key` entered in the prompt is not explicitly entered in the object created.

`let fruits = prompt("Enter")

let choice = {
  [fruits] : "Tasty"
}
alert(choice.apple) // output = "Tasty"   if you input apple in prompt`
// Using bracket notation to access and print
console.log(user["likes birds"]);  // Output: true`

### Using Object Computed properties to reassign values to it property

let person = new Object({
  name :'Prince',
  age : {
    class : "default"
  }
})
person["name"]["age"] = "done"

//This overwrite the current value of that property, otherwise it adds to it
### object shorthand property 
It can be used when the `key` name and the `variable` name is the same.

`let fruit = "orange"
let choice = {
  fruit // fruit : fruit
}
alert(choice.fruit) // output: "orange"`

### object Property names limitations
As reserved words cannot be used as a variable name, it does not apply to objects in JavaScript. 

For example:
`let user = {
  for : 2,
  let : 1
}`
The `key` variable name given to `user` obj are reserved words, but JavaScript object allowed reserved words to be used.
### Assigning Number as `key` in object
In general assigning number as key in JavaScript is not a good practice. One thing is accessing the value would mean converting the key `0` to string otherwise it does not get it value using the period `choice.0`

`let fruit = "orange"
let choice = {
  0 : fruit
}
alert(choice["0"])` // orange
alert(choice[0]) // output = orange. it's also converted to a string. 
**Note** : only numbers are converted into string.
### Property existence test (`in`) operator
It returns `true` if the property `key` exist. **NOTE** : when using `in` to check if a key exist, ensure the key is a `string`

Example:
`let user ={name : "Prince"};
`alert ("name" in user)// output : true, because the key exist.`

### The "for..in" loop
It's use to illiterate  an object, and returning it `key` in strings.

In the example below, the `key` of `obj` object are returned in `strings` the is why, we use the `[]` square bracket when accessing the properties. 

`let obj = {name : null, age : 56};
for(let x in obj) alert(obj[x])`

### How keys declared with numbers are returned 

`let codes = {
  "49": "Germany",
  "41": "Switzerland",
  "44": "Great Britain",
  // ..,
  "1": "USA"
};

for (let code in codes) {
  alert(code); // 1, 41, 44, 49
}`
The keys are returned in ascending order, but this does not implies for named index.

**Incase** where you want to maintain the arrangement of your keys when they are called append + to the number thereby making it not represented as number.
` let codes = {
  "+49": "Germany",
  "+41": "Switzerland",
  "+44": "Great Britain",
  // ..,
  "+1": "USA"
};

for (let code in codes) {
  alert( +code ); // 49, 41, 44, 1
}`

And when returning the output, appending +, converts it to number.

**Note** as much as object convert it keys to string, do not append unary operator directly to number as this is a syntax error.

+49 : "Germany"`
`
### Checking if the object created is empty
`function isEmpty(obj) {
  `for (let key in obj) {
    // if the loop has started, there is a property
    return false;
  }
  return true;
}`

### Multiply numbers in object
` let menu = {
  width: 200,
  height: 300,
  title: "My menu",
  arr : [2, 4, 89]
};

 function multiplyNumeric(obj){
  for(let key in obj){
    if(typeof obj[key] == "number"){
      obj[key] multiply= 2
    }
  }
 }
 multiplyNumeric(menu)`

### Comparison by reference 
`let a = {};
let b = a; // copy the reference

alert( a == b ); // true, both variables reference the same object
alert( a === b ); // true`

Both object can be `true` if they are referencing the same address.

### Cloning objects
`let user = {
  name: "John",
  age: 30
};

let clone = {}; // the new empty object

// let's copy all user properties into it
for (let key in user) {
  clone[key] = user[key];
}

// now clone is a fully independent object with the same content
clone.name = "Pete"; // changed the data in it

alert( user.name ); // still John in the original object

### Using Object.assign to clone
It's a build in function to clone objects.
With the syntax 
`Object.assign(dest, ...sources)`

`dest`: is the target (This is what actually clones the other objects)

`sources`: is the object to be cloned (it is automatically spread in the target)

`  let a = {name : "Prince"}
   let b = {age : 34}
  
   Object.assign(a, b)
   console.log(a)`

**Note:** if the copied property already exists, it get overwritten.


`let a = {name : "Prince"}
   let b = {age : 34}
  
   Object.assign(a, b, b)
   console.log(a) // {"name:Prince", age:34} `

### Using Object.assign to create a simple clone
`let user = {
  name: "John",
  age: 30
};

let clone = Object.assign({}, user);

alert(clone.name); // John
alert(clone.age); // 30`

*when using Object.assign to clone object, it does not clone the nested object, i.e you will still be using the reference of that nested object when changes occur it directly affect it.*

To avoid that you can use `structuredClone(user)`

`let user = {
  name: "John",
  sizes: {
    height: 182,
    width: 50
  }
};

let clone = structuredClone(user)
alert(clone.name)  `

### Limitation of structureClone
It cannot clone function as a property inside an object.

`let user = {
  name : "Prince",
 greeting(){
   return "Hi"
 }
}
let clone = structuredClone(user)
console.log(clone.name)` //it returns sharp error

### calling function from an object 

`let user = {
  name: "John",
  age: 30};

`user.sayHi = function() {
  alert("Hello!");
};`

`user.sayHi(); // Hello!`

### Part of an Object
The first two data are `properties` and the last two data are `object method`.

 const person = {
  name: ["Bob", "Smith"],
  age: 32,
  bio: function () {
    console.log(`${this.name[0]} ${this.name[1]} is ${this.age} years old.`);
  },
  introduceSelf: function () {
    console.log(`Hi! I'm ${this.name[0]}.`);
  },
};

### Using `this` keyword in object

let obj = new Object({
        name : "Prince",
        sayMyName(){
          console.log(`My name is ${this.name}`)
        }
      })
      obj.sayMyName()
      
  //`this` keyword in object refers to that property value in object.

### Accessing a function inside an object, and the object been contain in a function 

`function createPerson(name) {
  const obj = {};
  obj.name = name;
  obj.introduceSelf = function () {
    console.log(`Hi! I'm ${this.name}.`);
  };
  return obj;
}
`createPerson("Prince").introduceSelf() // Hi! I'm Prince`

### Instead of creating an object inside a function and returning that object to access it properties, you can use a function as a constructor.

` function person(name){
   this.name = name;
   this.introduceSelf = function(){
     console.log(this.name)
   } 
 }
 let  prince = new person('Prince')
 console.log(prince)`

**Note** ensure to include the `new` keyword when calling the function constructor.

### Pushing an object into an array using map
`let john = { name: "John", surname: "Smith", id: 1 };
let pete = { name: "Pete", surname: "Hunt", id: 2 };
let mary = { name: "Mary", surname: "Key", id: 3 };

let users = [ john, pete, mary ];

let userMapped = users.map(user=>({
  id : user.id, fullName : `${user.name} ${user.surname}`
}))
console.log(userMapped)`

**Note**
*As we remember, there are two arrow functions: without body value => expr and with body value => {...}.*

From the code above JavaScript would treat `{` as the start of function body, not the start of the object. So wrapping it with `({` would make JavaScript treat it as an `object`.