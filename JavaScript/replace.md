It's used to replace a character or word(s) inside a string and it returns a new string.

let myName = "Prince Samuel"
let mySurname = myName.replace("Prince", "Obot") 
console.log(mySurname) // "Obot Samuel"

**The replace method also support patterns.**

let myName = "Prince Samuel"
let mySurname = myName.replace("Prince", "Obot $&") 
console.log(mySurname) // "Obot Prince Samuel"

`$&` means the argument to be replaced. Appending `Obot` means replace `Prince` with `Obot Prince` ,.
It is just calling Prince and adding another word to it. 