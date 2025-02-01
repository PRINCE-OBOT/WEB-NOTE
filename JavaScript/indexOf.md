**indexOf** takes two argument, the value to search it index and the starting point.

`[1, 2, 2].indexOf(2, 3)`

*The above code begin from index 3 to search for the index of 2.*

### Usage in String
It is use to get the index of an `element` or `string character`.

`const num = "Okon, Grexk"
`console.log(num.indexOf('G'))` // 6

If the `string character` is not found it returns -1.

`const num = "Okon, Grexk"
`console.log(num.indexOf('H'))` -1

### Usage in Array
`const num = ["Okon", "Grexk"]
`console.log(num.indexOf('Okon'))` // 0

If the element is not found in the `array` it returns -1

`const num = ["Okon", "Grexk"]
`console.log(num.indexOf( 'Ok'))` -1
