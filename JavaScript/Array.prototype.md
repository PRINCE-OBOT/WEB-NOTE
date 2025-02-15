**Array.prototype** Is an object that has access to all the array method. 

#### If Array.prototype has access to all method, then how does a variable which is an array has access to those method too.

When you create an array, it inherits Array.prototype, not the methods directly. Since Array.prototype already has access to the methods, the array can use those method.

**Shorthand**

[].filter.call(arguments, (cur, next)=> cur + next ,0)