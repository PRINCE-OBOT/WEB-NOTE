Normally concatenating makes a copy of the multiple array elements and returns a new array.

`let male = ["Prince"]
let female = ["Ama"]
`let bothSex = `male.concat(female)
`console.log(bothSex)`

But concatenating `object` with array, number and other datatype, does not display the object in the return concatenated value when using `alert interaction`
*What to do?*

**Use the built-in-method**
As this makes `concat` treat the object as array, making it to display when `alerted`.
`[Symbol.isConcatSpreadable],
`length : 2` 
And setting the length tells how many elements above it will be displayed.

`let arr = [1, 2];

let arrayLike = {
  0: "something",
  1: "else",
  [Symbol.isConcatSpreadable]: true,
  length: 2
};

alert( arr.concat(arrayLike) );`