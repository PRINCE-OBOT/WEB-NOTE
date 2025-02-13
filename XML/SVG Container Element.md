Is used to group or organize SVG element. They do not represent visual content by themselves.

### `a` (anchor) 
For linking web pages 
`<a href="www.google.com">//
`Provide svg shape or text </a>`

| Attribute      | Description                                                            |
| -------------- | ---------------------------------------------------------------------- |
| href           | The URL to go to                                                       |
| download       | Tells the browser to download the URL instead of go to it              |
| hreflang       | The language of the page the link points to                            |
| referrerpolicy | The referrer to send when fetching the URL                             |
| rel            | The relationship of the target object to the link object               |
| target         | Where to open the link. Can be _self, _parent, _top, _blank, or a name |
| type           | The MIME type for the linked URL                                       |

### `def`(definition)
It is to avoid repeating of svg element
 `<defs>
  `<linearGradient id="gradient">
    `<stop offset="0%" stop-color="red" />
    `<stop offset="100%" stop-color="blue" />
  `</linearGradient>
`</defs>

The linear gradient color can be reused in different shapes using the **id** name, without re-creating another linear-gradient.

Example:
`<rect fill="url(#gradient)" rx="10" ry="10" width="100" height="100" />`


### `g` (Grouping) 
styles applied in the group element is inherited by all elements it contain accept explicitly change

  `<g fill="red">
  `<rect x="3" y="3" width="10" height="10" />
  `<circle cx="16" cy="7.5" r="3" />
 `</g>

The color red is `filled` into `rect` and `circle` shapes.

### `marker`
It is used to add simple shapes around shapes, mostly used for arrowhead

` <defs>
    `<marker id="arrow" markerWidth="30" markerHeight="10" refX="10" refY="0" orient="auto">
    `<path d="M0,0 L10,5 L0,10 Z" fill="red" />
    `</marker>`
`</defs>`

` <path d="M50,100 L300,100" stroke="black" stroke-width="2" marker-start="url(#arrow)" />`

**markerWidth:** defines the viewBox width of the content (Arrow head in this case).

**markerHeight:** defines the viewBox height of the content (Arrow head in this case).

**refX**: 0 means the start point of the `L` arrowHead, when increase it pushes the shape backward.

**refY**: 0 means the start point of the `L` arrowHead, when increase it changes the position relatively to the arrowHead vertically.

**orient:** It is used for orientating the shape, `auto` means way the shape is draw, it can be 20, 40...

___The you can call it to the shapes___ using **marker-start, marker-mid or marker-end**

**Note** : In order to provide the **marker-mid**, your shapes or line must have a mid part.

| Attributes   | Description                                                                                                                          |
| ------------ | ------------------------------------------------------------------------------------------------------------------------------------ |
| id           | The unique id for the marker                                                                                                         |
| markerHeight | The height of the marker. Default is 3                                                                                               |
| markerWidth  | The width of the marker. Default is 3                                                                                                |
| refX         | The x position where the marker connects with the vertex. Default is 0                                                               |
| refY         | The y position where the marker connects with the vertex. Default is 0                                                               |
| orient       | The orientation of the marker relative to the shape it is attached to. Can be "auto", "auto-start-reverse" or an angle. Default is 0 |
### `mask` 
It is used to determine which shape should be displayed or not

1. Black (fill="black") → Fully Transparent

The shape, images or text will not be visible inside the masked shape.

2. White (fill="white") → Fully Visible

The shape, images or text will be visible inside the masked shape.

3. Gray (fill="gray") → Partial Transparency

Any shade of gray results in partial transparency.

Example: fill="rgb(128,128,128)" or fill="gray" makes the element 50% transparent.

4. Alpha (Opacity) Matters

You can use fill="white" opacity="0.5" to make an area semi-transparent instead of using gray.

5. Default Background of the Mask is Black

If a mask doesn’t fully cover an element with white or gray, the default black background will make the rest of the element fully transparent.

  `<defs>`
    `<mask id="myMask">`
      ` <rect x="0" y="0" width="400" height="200" fill="white" />` // This will not be visible as the color is white
      `<circle class="cir" cx="200" cy="100" r="50" fill="black" />`
     `</mask>`
`</defs>`

  `<rect class="content" x="50" y="50" width="300" height="50" fill="orange" mask="url(#myMask)" />`//The shapes is then called here.
  
**Note**: The position of the mask item is relative to svg viewBox.


### Pattern

**Attributes** 

**id**: it uniquely identifies the pattern, and it is use to reference the element that uses the id.

**width && height**: it act as a sub-viewBox for element the pattern would contain.

**patternUnits**: It can either be *userSpaceOnUse* or *object...*

It is set to **ObjectBoudingBox** by default. It fills up the shape relatively to it own width and height.
   **How pattern width and height work**
1. The value of width and height of the pattern falls between **0 and 1 (as 0.1 means 10%, 0.2 means 20% ... n), the percentage is calculated relative to the shape that contains the pattern's `id 
`<pattern width="0.1" height="0.1">
`</pattern>`

**How width and height of pattern children behaves**

The value of the width and height is more intuitive when the value is:
1. in percentage, that is relative to proportion of the pattern width and height, where 1% occupies 1% of the pattern width/height.

2. In integer, that is relative to the proportion of width and height shape that contain the pattern **id**.

**userSpaceOnUse**: fills up the shape relatively to the **SVG** viewBox.


`<defs>
`<pattern id="checkboard" width="200" height="105" patternUnits="userSpaceOnUse">
`<rect x="0" y="0" width="95" height="100" fill="black" />
`<rect x="100" y="0" width="95" height="100" fill="white" />
 `</pattern>
  `</defs>

`<rect fill="url(#checkboard)" x="3" y="3" width="40" height="40"/>`

**The `rect` element inside the pattern element share the width and height for themselves.**


### switch 
works as the regular switch statement, it return one of what meet the condition

#### Attributes to Use

**requiredFeatures**: Checks if a specific feature is supported by the browser.

**requiredExtensions**: Checks if a specific extension is supported.

**systemLanguage**: Matches based on the language of the user’s system.

 **Using** `systemLanguage`

`<svg width="200" height="100">
  `<switch>
    `<text systemLanguage="en" x="10" y="30">Hello</text>
    `<text systemLanguage="en-NG" x="10" y="30">Hola</text>
   `<text x="10" y="30">Default Text</text>
  `</switch>
`</svg> `

**The content that pass the test fit relative to the `SVG` width and height.**

**Using** `requiredFeatures` 

`requireFeatures` is not reliable in most browsers as it does not actually rely on the condition giving rather it just runs the first condition.

**Example**:
`<switch>
    <!-- This will render only if the browser supports gradients -->
    `<text requiredFeatures="http://www.w3.org/TR/SVG11/feature#Gradient" x="10" y="50" font-size="24">
      Your browser supports gradients!
    `</text>
    <!-- Fallback -->
    `<text x="10" y="80" font-size="24">
      `Gradients are not supported on your browser.
    `</text>
 `</switch> `

 
   ***Altered***
`<text requiredFeatures="http://www.w3.org/TR/SVG11/" x="10" y="50" font-size="24">
      Your browser supports gradients!
`</text>
    
*Altering the first `requireFeature` attributes does not actually make the second `requireFeature` attributes execute.

**Note**: The attributes of `switch` as not consistent and reliable as many browser does not check for the validation of the condition (Same thing applicable to `requireExtension`. 

### Symbol
basically use for re-using shapes 

`<symbol id="circleIcon" viewBox="0 0 50 50">
   `<circle cx="25" cy="25" r="30" fill="blue" />
`</symbol>
 `<use xlink:href="#circleIcon" x="0" y="0" />`
 // `<use href="#circleIcon" x="0" y="0" />`

**Note**: Ensure to use the `xlink:href` (for old browser) or `href` (updated browser) when using the `use` property. 

### clipPath

clipPath is used to specify the part of the shape that will be visible. 

Clipping is when you remove a part from an element.

For clipping, we use the `<clipPath>` element.

Every path/element inside a `<clipPath>` element is inspected and evaluated. Then every part of the target that lies OUTSIDE of this area will NOT be rendered. In other words: Anything outside the path is hidden and anything inside is shown!

`<defs>
    `<clipPath id="cut-bottom">
      `<rect x="0" y="0" width="200" height="50" />
    `</clipPath>
  `</defs>
  `<circle cx="100" cy="100" r="100" fill="red" clip-path="url(#cut-bottom)" />`