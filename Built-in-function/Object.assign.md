## Using Object.assign to clone
It's a build in function to clone objects.
With the syntax 
`Object.assign(dest, ...sources)`

`dest`: is the target (This is what actually clones the other objects)

`sources`: is the object to be cloned (it is automatically spread in the target)

`  let a = {name : "Prince"}
   let b = {age : 34}
  
   Object.assign(a, b)
   console.log(a)`
   
### Side effects 
It does not clone nested array, as they still make reference to initial variable 