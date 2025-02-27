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

The `scale(sx, sy)` function is used to scale an object by `x` and `y`. If `y` is not provided, it is set to be equal to `x`.

The `scale()` function is used to change the size of an object. It takes two numbers: the x scale factor and the y scale factor. The x and y scale factors are taken as the ratio of the transformed dimension to the original. For example, 0.5 shrinks the object by 50%.
**1 is default 

**Flipping shapes**
scale(1, -1) *vertical scaling*
scale(-1, 1) *horizontal scaling

#### To combine `translate` and `scale` and get the expected behaviour.

*`Translate` should appear before `scale`*

`translate()
`scale()`

*When translate is placed after scale, the values of translate(10, 0) is been added base on the scale **sx, sy** value, if scale is (2, 1) the translate value then becomes translate(20, 0)* 

#### To combine `translate, rotate` and `scale` and get the expected behaviour

*It should be arranged like*

`translate() 
`rotate() 
`scale()`

#### **How to combine `translate, scale` and `rotate` get 3D behaviour

*Rotate should appear after scale*

`translate()  
`scale(2, 1)
`rotate()

**This behaviour is applicable when the pivot is placed outside of the shape or image. While the shape rotates,** it also **skew** by the **sx** or **sy** axis with the highest value.


![[Screenshot_2025-02-15-12-25-51-15_e3c1f266f17b29c7b40472751f031275.jpg]]

![[Screenshot_2025-02-15-12-25-51-15_e3c1f266f17b29c7b40472751f031275.jpg]]
**Note** the scale **sx** and **sy** values should not be the same to get the expected **3D** effects.

#### Rotate() Function

The `rotate()` function is used to rotate an object by a `degree`.

**Default** `rotate(0)`

`<rect x="50" y="5" width="40" height="40" fill="blue" transform="rotate(45)" />`

#### Skew() Function

The `skew()`function is used to skew an object along the `x` or `y` axis by a `degree`.

**Default** `skewX(0), skewY(0)`

**Formula**
*dx = y `*` tan(x°)*

If skewX is **1** degree. 

tan(1°) ≈ 0.01745

`dx = y * 0.01745`
`dy = x * 0.01745`

#### How to move skew effectively 

*First thing to consider is:* how far I want my skew to be from my **x** or **y** axis.

Let's say I want to bottom-left rect to be move by **10 unit** from the x axis

If the bottom-left axis is at point **25** unit
#### Finding a value that when multiplied by `25`will produce `10 unit`

Divide the bottom-left y axis value(25) by 10.

If the y axis bottom-left value is 25

10/25 = 0.4
#### Finding the skewX `value` ...

*Use calculator to find the inverse of **tan**

`tan⁻¹(0.4)` = 22.9 //using calculator
       **Or**
`Math.atan(0.2) * (180 / Math.PI)` = 22.9 //using JavaScript 

**skewX(22.9)

*So, therefore*
`25 * 0.4 = 10
`dx = 10`

*Providing two coordinates skew value
`<rect x="5" y="5" width="40" height="40" fill="blue" transform="skewX(30),skewY(30)" />

#### Matrix() function 

Transformation **matrix** is a matrix that transforms one vector into another vector in the process of matrix multiplication. 

*Transforming the vector from one vector to another means, **Collecting the initial input such as the `position, coordinate or size` and returning a new `position, coordinates or size` for the element.

So, it is a convenient tool for applying SVG transformations like **translation**, **rotation**, **scaling**, and **skewing**. Transformation matrices are based on linear algebra, which offers a mathematically elegant way to express complex transformations.

#### Transformation Matrix

The transformation matrix is 3x3, combining translation, scale, rotation, and skew transformations. Here’s what each element represents:

![[Pasted image 20250217125059.png]]

**a** – it can be a scaling factor in the x-direction, usually denoted as _**sx**_ or the cosine value _**cos(α)**_ of the angle to rotate  
**b** – it can be _**tan(α)**_ skewing factor in the y-direction or the sinus value _**sin(α)**_ of the angle to rotate  
**c** – it can be _**tan(α)**_ skewing factor in the x-direction or the sinus value _**-sin(α)**_ of the angle to rotate  
**d** – it can be scaling factor in the y-direction is usually denoted as _**sy**_ or the cosine value _**cos(α)**_ of the angle to rotate  
**e** – translation along the x-direction is usually denoted as _**tx**_  
**f** – translation along the y-direction is usually denoted as _**ty**_

The transformation matrix allows you to get new coordinates of the object’s points (_x new_, _y new_) during the transformation by multiplying it by the values of the previous coordinates (_x prev_, _y prev_):

![[Pasted image 20250217154705.png]]

#### Translation Matrix

The **translation** is a transformation in SVG that moves all the points of an object at the same distance along parallel lines.

**Formula for translation

_x(new) = a·x(prev) + b·y(prev) + e 

_y(new) = b·x(prev) + d·y(prev) + f 

`transform="matrix(1 0 0 1 0 25)"


#### Scaling Matrix

Scaling is an SVG transformation that enlarges or reduces an object using a scaling factor.

#### Rotation Matrix

If you like to practice calculating sines and cosines, you are here! The rotation matrix looks like this:

![[Pasted image 20250217192537.png]]

#### Regenerating a different pivot

*Formula for placing the pivot*

`e = cx - cx•cos(ø) + cy•sin(ø)`

`f = cy - cx•sin(ø) -cy•cos(ø)`


**x point**: where the pivot should be position in the x-axis. Assuming we want the pivot to be placed at **25** unit away from the x-axis.


e = 25 - (25 `*` )