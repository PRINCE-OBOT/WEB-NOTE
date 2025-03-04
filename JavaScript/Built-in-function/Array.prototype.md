
### Using Array.prototype
This is useful when the object type is not an `array`
*ensure to provide the length on which the operation will be carried on.*

`const obj = {
  0 : 23,
  1 : 78,
  2 : 77,
  Hi : 8,
  length : 2
}

`let itera = Array.prototype.map.call(obj, x=> x * 2)
`console.log(itera)`