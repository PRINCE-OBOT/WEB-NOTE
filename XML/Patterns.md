### Attributes
**id**: it uniquely identifies the pattern, and it is use to reference the element that uses the id.

**width && height**: it defines the size of each tiles that any element the pattern would contain.

**patternUnits**: It can either be *userSpaceOnUse* or *object...*

It is set to *object...* by default meaning it does not fill up the width and height element that is reference with the pattern tile.

**userSpaceOnUse**: fill up the width and height that is reference with the pattern tile.


`<defs>
`<pattern id="checkboard" width="200" height="105" patternUnits="userSpaceOnUse">
`<rect x="0" y="0" width="95" height="100" fill="black" />
`<rect x="100" y="0" width="95" height="100" fill="white" />
 `</pattern>
  `</defs>

**The `rect` element inside the pattern element share the width and height for themselves.**