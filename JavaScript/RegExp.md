It is also used to search for word, but it is more flexible and dynamic.L because it can be use with other method


**Use case with Match()**

let myName = "New year Hurray"
let mySurname = myName.match(RegExp(/Hurray/i))
console.log(JSON.stringify(mySurname)) // ["Samuel"]

**Use case with replace()

let myName = "new year Hurray"
let mySurname = myName.replace(RegExp(/Hurray/i), ", new life")
console.log(JSON.stringify(mySurname)) // "new year, new life"

