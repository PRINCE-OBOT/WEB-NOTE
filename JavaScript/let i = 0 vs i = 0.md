`let myArr = [1, 4, 8]
for(i = 0; i<myArr.length; i++){
  console.log(myArr[i])
}`

The code above works very well without including `let i= 0`

*The code below does not work, why? Because you just told `i` that you will provide a value for it and now you are taking the value below it, making the value inaccessible. TO AVOID THIS MAKE SURE TO USE `let i = 0` whenever you declares `i` in a loop, so that `i` will stick to it own value in his scope*

`let myArr = [1, 4, 8]
for(i = 0; i<myArr.length; i++){
  console.log(myArr[i])
}

let i = 2;`