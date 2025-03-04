Convert a number to positive regardless of the sign.

`console.log(Math.abs(-5));   // Output: 5
console.log(Math.abs(5));    // Output: 5
console.log(Math.abs(0));    // Output: 0
console.log(Math.abs(-3.14)); // Output: 3.14
console.log(Math.abs("10")); // Output: 10 (string is converted to number)
console.log(Math.abs("-10")); // Output: 10
console.log(Math.abs(null)); // Output: 0 (null is coerced to 0)
console.log(Math.abs("foo")); // Output: NaN (non-numeric string)
console.log(Math.abs());      // Output: NaN (no argument provided)`