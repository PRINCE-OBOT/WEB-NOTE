It check if a string has the search word and return the array of the search word, else null.

---------This match pattern-------
let myName = "Prince Samuel"
let mySurname = myName.match(/Samuel/i) 
console.log(mySurname) // ["Samuel"]


  ----and this match pattern----
       
let myName = "Prince Samuel"
let mySurname = myName.match("Samuel") 
console.log(mySurname) // ["Samuel"]


----Performance the same task, but `//` allows for use of flags(i, g).----




### Patterns
let myName = "New Year, Hurray"

`/H...ay/` // Matches `Hurray` in the string or any other word with any word that can replace the three characters.

`/r{2}/` // Matches the character `r` that are join together.

`/.{2}/` // Matches any first two characters from the beginning of the string by default.

`/^.{2}/` // Explicitly forcing it to match from the beginning.

`/.{2}$/` // Matches any two characters from behind.
