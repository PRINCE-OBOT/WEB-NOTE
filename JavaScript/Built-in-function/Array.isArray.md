`console.log(typeof []) //object
`console.log(typeof {})`//object

Remember, `array` is a type of object, but because they are use very often they have there own built-in-method to check if the type of `object` is an `array` .

If the type of object is an array it returns `true` else `false`
`console.log(Array.isArray([])) //true
`console.log(Array.isArray({}))`// false