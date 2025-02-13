
Is used to arrange elements in ascending, descending or other orders.


`function example2(arr) {
 `return arr.sort((a, b)=> a > b ? 1 : -1)`
}
`console.log(example2(["Prince", "prince", "B", "a"])); 

#### Behaviour of sort

1. Since capital letter comes before small letter in ASCII, capital letter are sorted first before small letter.

2. If the element are converted to small letters, as in 
    `arr.sort((a, b)=> a.toLowerCase() - b.toLowerCase())` All letters are treated equally, but 

3. If they exist two or more elements that is case-sensitive in the array, as in:
  ["apple", "Apple", "ball" ] the sorting for this two elements will work base on **ASCII code** that is the capital letter comes first regardless of the `.toLowerCase()` inside the sort function.
  
## Either method can be use to sort alphabet
`arr.sort()` 

*Or*

`arr.sort((a, b)=>a > b ? 1 : -1)`

### How to sort numbers
`arr.sort((a, b)=> a - b)`
