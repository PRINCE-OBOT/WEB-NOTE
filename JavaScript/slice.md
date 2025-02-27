It is used to extract a character from a string or an elements from an array.

`let arr = ["t", "e", "s", "t"];

 `slice(start, end)`
 
alert( arr.slice(1, 3) ); // e,s (copy from 1 to 3)

alert( arr.slice(-2) ); // s,t (copy from -2 till the end)`

//-2 means from the last two elements downwards.

//-1 means from the last one elements downwards.

**Note**
If there is no argument inside the slice method, it makes a copy of the `arr`