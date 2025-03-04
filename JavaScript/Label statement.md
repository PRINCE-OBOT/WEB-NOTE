A label statement in JavaScript is an identifier followed by a colon (:) that you can use to mark a block of code. It is mainly used with break and continue to control the flow of loops, especially when dealing with nested loops.

**Syntax:

labelName: statement;

*labelName is the custom name you give to the block of code.

**statement is usually a loop or block of code.

```
let arr = [1, 4, 6, 17, 13, 8]

▶️here : for(i = 0; i <arr.length; i++){
   for(let j = 0; j < arr.length; j++){
   if(i > 3) break here; ▶️
    }
  }
```

**From the code** the loop breaks from the inner pause button (`here` label) to the outer pause button (`here` label). Breaking through the nested loop.