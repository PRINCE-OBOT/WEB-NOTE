
### Combining map, filter, and reduce

` let arr = [3, 6, 8, 5]
 
 function sumTripleEvent(arr){
   return arr
   .filter((val)=> val % 2 === 0)
   .map(x=>x*3)
   .reduce((acc, product)=> acc + product, 0)
 }
 console.log(sumTripleEvent(arr))`

### Usage of filter callback with property function in object.

`let army = {
  minAge: 18,
  maxAge: 27,
  canJoin(user) {
    return user.age >= this.minAge && user.age < this.maxAge;
  }
};

let users = [
  {age: 16},
  {age: 20},
  {age: 23},
  {age: 30}
];

// find users, for who army.canJoin returns true
let soldiers = users.filter(army.canJoin, army);

alert(soldiers.length); // 2
alert(soldiers[0].age); // 20
alert(soldiers[1].age); // 23`

*If in the example above we used users.filter(army.canJoin), then army.canJoin would be called as a standalone function, with this=undefined, thus leading to an instant error.*

**OR**

Replace the filter callback function with.

`let soldiers = users.filter(user => army.canJoin(user))`

### Passing function through a Map method

`function addOne(num) {
  return num + 1;
}
`const arr = [1, 2, 3, 4, 5];
`const mappedArr = arr.map(addOne);
`console.log(mappedArr); // Outputs [2, 3, 4, 5, 6]`


### map
If you are to return the same number of array elements, without having to extract from the array elements, `use map`
**Shorthand** to convert datatype using map, `map(Number)`, `map(String)`;
### reduce 
If you are to compress values inside the array to a single or small subset value, `use reduce`

**Using reduce with `string`

`const words = ['Hello', 'world', 'from', 'reduce'];
`const sentence = words.reduce((result, word) => result + ' ' + word, '');
`console.log(sentence); // Output: " Hello world from reduce"  `

### sort 
This explanation tend to conflit with map but know that, sorting rearranges the array elements, It arranges element in order without extracting from the array elements

//This code sort the array using the last letter of the first name.

`let myName = ['Prince, Obot', 'Justice, Uwaje', 'Sunday, Daniel', 'Friday, Amarachi', 'Sabastine, Richard']

let filt = myName.sort((a, b)=>{

//This line of code is here so as to provide a means for sorting.

let [afirst] = a.slice(a.indexOf(', ')-1, a.indexOf(', '))
let [bfirst] = b.slice(b.indexOf(', ')-1, b.indexOf(', '))

return afirst > bfirst ? 1 : -1
})
console.log(filt)`
### filter
Use filter when you want to extract from an array, the element that meets the condition.
