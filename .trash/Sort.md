
Is used to arrange elements in ascending, descending or other orders.


`function example2(arr) {
 `return arr.sort((a, b)=> a === b ? 0 : a > b ? 1 : -1)`
}
`console.log(example2(["Prince", "prince", "B", "a"])); 

#### Behaviour of sort

1. Since capital letter comes before small letter in ASCII, capital letter are sorted first before small letter.

2. If the element are converted to small letters, as in 
    `arr.sort((a, b)=> a.toLowerCase() - b.toLowerCase())` All letters are treated equally
  
## Either method can be use to sort alphabet
`arr.sort()` 

*Or*

`arr.sort((a, b)=> a === b ? 0 : a > b ? 1 : -1)`
