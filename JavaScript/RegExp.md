It is also used to search for word, but it is more flexible and dynamic because it can be use with other method and it accept variable name, without relying of a static string or number.


**Use case with Match()**

let myName = "New year Hurray"
let mySurname = myName.match(RegExp(/Hurray/i))
console.log(JSON.stringify(mySurname)) // ["Samuel"]

**Use case with replace()

let myName = "new year Hurray"
let mySurname = myName.replace(RegExp(/Hurray/i), ", new life")
console.log(JSON.stringify(mySurname)) // "new year, new life"

*If you have to declare RegExp as standalone with having to fix it inside of other method use the `new Keyword`

Example 
`let exp = new RegExp(item, "gi")`