### Patterns
let myName = "New Year, Hurray"
`\`     // Escape character
`\d`   //find a digit
`\s`   //find a whitespace character
`1+` //Filters all number `1` 
from the string
`\b`  //find match at beginning `/\bcat/`or end `/cat\b/` of a word     
`n+`  //Find `n` from the beginning and also returns multiple `n` if they are join together 
`n`    // Finds `n` from the beginning and returns it separately 

`n*`  //Find `n` from the beginning and returns also returns multiple  `n` if they are join together. **Note** : it returns  empty string `""` if the search is not found.

`n?` //It works the same `n*` because it returns an empty string if the search is not found, but it returns the search character separately.

`/H...ay/` // Matches `Hurray` in the string or any other word with any word that can replace the three characters.

`/r{2}/` // Matches the character `r` that are join together.

`/.{2}/` // Matches any first two characters from the beginning of the string by default.

`/^.{2}/` // Explicitly forcing it to match from the beginning.

`/.{2}$/` // Matches any two characters from behind.

`/a|b/`   //a or b 
**It first find `r` if it does not find it, then find the next match `P`

`const myName = 'Prince'`
`myName.match(/r|P/)` // ['P']

`[a-z]` //Returns all character that falls between the range.

`[0-9]` //Returns all number that falls between the range.

`[^abc]` //Return character that are     not in this range

`const myName = 'Prince'`
`myName.match(/[^abc]/)` // ['P', 'r', 'i', 'n', 'e'] 

### Using`1+` as grouping

"aabbc".match(/([^])/ || []) // ['a', 'a', 'b', 'b']

"aabbc".match(/([^])\1+/ || []) // groups element that is more than one, **note**: the element of the same type of must be together *example* not like this ['a', 'b', 'b', 'a'] for proper grouping.

The results of the above code becomes ['aa', 'bb']

`[^]` : it matches everything in the string into an array.