### Patterns
let myName = "New Year, Hurray"
`\`     // Escape character
`\d`   //find a digit
`\s`   //find a whitespace character
`\b`  //find match at beginning `/\bcat/`or end `/cat\b/` of a word     
`n+`  //Find `n` from the beginning and also returns multiple `n` if they are join together 
`n`    // Finds `n` from the beginning and returns it separately 

`n*`  //Find `n` from the beginning and returns also returns multiple  `n` if they are join together. **Note** : it returns  empty string `""` if the search is not found.

`/H...ay/` // Matches `Hurray` in the string or any other word with any word that can replace the three characters.

`/r{2}/` // Matches the character `r` that are join together.

`/.{2}/` // Matches any first two characters from the beginning of the string by default.

`/^.{2}/` // Explicitly forcing it to match from the beginning.

`/.{2}$/` // Matches any two characters from behind.
