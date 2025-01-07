**Please note that methods sort, reverse and splice modify the array itself.**

### sort
Using sort more conveniently

`function filterSort(arr){
  return arr
``  .filter((val)=> val.rating >= 4.5)
``  .sort((a, b)=> a.title > b.title ? 1 : -1)
}
`console.log(filterSort(books))`

## -

## Either method can be use to sort alphabet
`arr.sort()` 

*Or*

`arr.sort((a, b)=>a > b ? 1 : -1)`

### How to sort numbers
`arr.sort((a, b)=> a - b)`
