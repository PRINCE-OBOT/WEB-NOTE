*Understanding Fisher Yate method - you should understand `index` position and the actual `element` value. 

`j` returns a random value between `0` to the value of `i` inclusive 

And only two `index position` is swapped, which is the `index` position of `i` and the random `index` of `j`

`let arr = [1, 2, 3];

for(i=arr.length-1; i>0; i--){
  let j = Math.floor(Math.random()*i+1)
 
 let k = arr[i]
 arr[i] = arr[j]
 arr[j] = k
}
console.log(arr)`

### Using Destructuring
`let arr = [1, 2, 3, 6]

for(i=0; i<arr.length; i++){
  let j = Math.floor(Math.random()*i+1);
 
[arr[i], arr[j]] = [arr[j], arr[i]]
}
`

### How sort() works
sort(): when defined like this without a `comparison function` it converts the element inside the array into a strings and uses there UTF-16 code to sort them.

If there `comparison function` is included, it uses the element value to determine if when both element is been subtracted returns negative or positive, 
`negative` : stay where you are.
`positive` : interchange position.
`equal` : maintain your initial position.

In cases like,
`arr.sort(()=>Math.random - 0.5)`
*First thing to understand is ,Math.random is a value itself ranging from 0.1 -0.9, that subtract 0.5, that means the result of the expression can either be positive, negative, equal. Even though argument are not explicitly specified in the sort method, as in `(a, b)` it uses implicitly specified by JavaScript. then the value returned from the expression is used to check if it either positive or negative to swap the array elements*

### Demo to check occurrence, when using sort() without explicitly defining the comparison function 
`function checkSortProcess(arr){
  arr.sort(()=> Math.random() - 0.5)
}

let obj = {
  '479' : 0,
  '497' : 0,
  '947' : 0,
  '974' : 0,
  '749' : 0,
  '794' : 0
}

for(i=0; i<200; i++){
let array = [4, 7, 9]
checkSortProcess(array)
obj[array.join('')]++
}

for(let key in obj){
  alert(`${key} : ${obj[key]}`)
}`