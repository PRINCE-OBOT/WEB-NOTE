### fill

Defines the color of the shape 

### fill-rule

The `fill-rule` attribute defines the algorithm to use to specify the inside part of a shape. By default it's **nonzero**.

#### How **nonzero** is calculated

What to consider if you want few part of the shapes to be either **coloured** or **removed coloured**

The shapes starting from the innermost one to the outer shape, should be drawn in an order of **clock-wise and counter-clockwise.

#### How **evenodd** is calculated.

*If after counting from the innermost shape to the outer shape is an even number **Only even number shapes** are coloured otherwise**remove color**.

*If after counting from the innermost shape to the outer shape is an odd number **Only odd number shapes** are coloured otherwise**remove color**.

### fill-opacity

fill-opacity property defines the opacity of the fill color.

(legal range: 0 to 1)
### stroke-opacity 

stroke-opacity 
property defines the opacity of the stroke color

(legal range: 0 to 1)

### opacity 

The opacity attribute defines the opacity of the circle

### stroke-width

stroke-width defines the width of the stroke.

### stroke-linecap Attribute

The `stroke-linecap` attribute defines different types of endings for a line or an open path.

The `stroke-linecap` attribute can be used with the following SVG elements: `<path>`, `<polyline>`, `<line>`, `<text>`, `<textPath>`, `<tref>` and `<tspan>`.

The value of the `stroke-linecap` attribute can be "butt", "round" or "square".

Here we use the `stroke-linecap` attribute to set different endings for three lines:

### stroke-dasharray

The **stroke-dasharray** attribute is used to create dashed lines.

The `stroke-dasharray` attribute can be used with the following SVG elements: `<circle>`, `<ellipse>`, `<line>`, `<path>`, `<polygon>`, `<polyline>`, `<rect>`, `<text>`, `<textPath>`, `<tref>` and `<tspan>`.

The value of the `stroke-dasharray` attribute can be "none" or a comma or space separated list of lengths/percentages that define the lengths of dashes and gaps.

Here we use the `stroke-dasharray` attribute to create different dashed lines:


**The first number represents the length of the dash.

**The second number represents the length of the gap.

*If more numbers are provided, they repeat in sequence.

### stroke-linejoin 

The `stroke-linejoin` attribute defines the shape of the corners where two lines meet.

The `stroke-linejoin` attribute can be used with the following SVG elements: `<path>`, `<polygon>`, `<polyline>`, `<rect>`, `<text>`, `<textPath>`, `<tref>` and `<tspan>`.

The value of the `stroke-linejoin` attribute can be "arcs", "bevel", "miter", miter-clip" or "round".

Here we use the `stroke-linejoin` attribute to create different corner shapes:
### stroke

stroke defines the color of the line/border.

### use 

It is used to avoid code duplicate

`<use x="-10" y="-10" href="#arrow" stroke="pink"/>`

### Transformations

SVG elements can be manipulated using transform functions.

The `transform` attribute can be used with any SVG element.

The `transform` attribute defines a list of transform functions that can be applied to an element and the element's children:

- `translate()`
- `scale()`
- `rotate()`
- `skewX()`
- `skewY()`
- `matrix()`

---

#### Translate() Function

The `translate()` function is used to move an object by `x` and `y`.

Assume one object is placed with x="5" and y="5". Then another object contains transform="translate(50 0)", this means that the other object will be placed at x-position 55 (5 + 50) and at y-position 5 (5 + 0).

#### Scale() Function

The `scale()` function is used to scale an object by `x` and `y`. If `y` is not provided, it is set to be equal to `x`.

The `scale()` function is used to change the size of an object. It takes two numbers: the x scale factor and the y scale factor. The x and y scale factors are taken as the ratio of the transformed dimension to the original. For example, 0.5 shrinks the object by 50%.
**1 is default 

#### Rotate() Function

The `rotate()` function is used to rotate an object by a `degree`.

`  <rect x="50" y="5" width="40" height="40" fill="blue" transform="rotate(45)" />`


#### SkewX() Function

The `skewX()` function is used to skew an object along the `x` axis by a `degree`.

`<rect x="5" y="5" width="40" height="40" fill="blue" transform="skewX(30)" />`

*Providing two coordinates skew value
`<rect x="5" y="5" width="40" height="40" fill="blue" transform="skewX(30),skewY(30)" />

