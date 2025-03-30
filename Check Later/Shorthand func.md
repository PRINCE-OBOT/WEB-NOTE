```js

let func = [(k, j)=> k+j]
let arr = []
func.forEach((_)=> arr.push(func[0](10, 40)))

console.log(arr)
```