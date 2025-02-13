`<text>` element is used to define a text.

**The `<text>` element has seven basic attributes to position and rotate the text:**

**x**	The x position of the start of the text. Default is 0

**y**	The y position of the start of the text. Default is 0

**dx**	The horizontal shift position for text (from previous text position)

**dy**	The vertical shift position for text (from previous text position)

**rotate**	The rotation (in degrees) applied to each letter of text

**textLength**	The width that the text must fit in

**lengthAdjust**	How the text should be compressed or stretched to fit the width defined by the textLength attribute

**Why use `dx` 

`<svg width="200" height="100">
  `<text x="20" y="50">
    `<tspan dx="0">Hello</tspan>
    `<tspan dx="10">World</tspan>
 `</text>
`</svg>`

**How transform work with text**

`<text x="40" y="40" transform="rotate(90 20 80)">Clicked here</text>`

Understanding how transform work with text.

*what to consider?* **The Initial coordinates of the SVG text,** in this case **40,40** and the **coordinate define in the transform**, in this case which **20,80** 
Then place your compass pin on the **transform** coordinates and extend the pen in the compass to the **text** coordinates then draw a circle.

The circle draw provide the circumference that the text with rotate through.

### tspan

`tspan` exist inside of a `<text></text>`SVG property.

It behave as normal `html` span, basically used for styling a part of a text.

The value of `dx` is relative to the previous text position.

### textPath

The `<textPath>` element is used to render a text along the shape of a path.

The `<textPath>` element has six basic attributes:

| Attribute    | Description                                                                                                                                    |
| ------------ | ---------------------------------------------------------------------------------------------------------------------------------------------- |
| href         | The URL to the path to render the text                                                                                                         |
| lengthAdjust | How to compress or stretch the text to fit the width defined by the textLength attribute. Can be spacing\|spacingAndGlyphs. Default is spacing |
| method       | How to render the glyphs along the path. Can be align\|stretch. Default is align                                                               |
| spacing      | The space between glyphs. Can be auto\|exact. Default is exact                                                                                 |
| startOffset  | How far the beginning of the text should be offset from the beginning of the path. Can be a length, percentage or a number                     |
| textLength   | The width of the text along the path. Can be a length, percentage or a number. Default is auto                                                 |
`<text fill="red">
  `<textPath href="#textP">Running aling tge line</textPath>
 `</text>`