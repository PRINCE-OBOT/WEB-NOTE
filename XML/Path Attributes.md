### Path L (M70 10 L20 20 L30 30 Z) - LINE TO
**--- It has 2 value**

**M10** : 70 unit away from the **x - axis** 
**M10** :  10 unit away from the **y - axis** 

**L20** : The first L20 means - draw a line of 20 units long away from the *x - axis*.

**20**: The first 20 means - The endpoint of the line drawn will be 20 unit away from the *y - axis*

------After that --
The next  **L**  does not actually draw a line, it specify how far the line will be away from the *x - axis* 

**L30** : Set 30 unit away from the *x - axis* 

**30** : Create 30 unit away from the *y - axis*, creating the point of intersection for the last endpoint to join to.

### Path Q (M2 2 Q8,2 8,8)  Quadratic Bezier Curve
**--- It has 2 value**

**Note** : It has one control point, when the coordinates is set to **Q8,2** the control point is then set at that point, which is **Q8,2**, and not the curve itself.

The control point is what moves the arc around.

The **8,8** specify how long the line length will be, which is *8*.

And the second 8 specify how further away it is from the y - axis.

### Path C (M2,2 C2,8 0,9 8,2) - CUBIC BEZIER CURVE 

**--- It has 3 value**
**The cubic bezier curve***

 C Attributes in SVG Path: A

Breakdown

C in SVG path data represents a cubic Bézier curve. It's a powerful tool for creating smooth, curved shapes. Here's a breakdown of its syntax and how it works:

Syntax:

C x1 y1 x2 y2 x y

x1, y1: Coordinates of the first control point.

x2, y2: Coordinates of the second control point.

• x, y: Coordinates of the endpoint of the curve.

### Path A (Elliptical arc)
--- It has 7 values 
The `A` attribute in the `<path>` 
element of SVG is used to draw an elliptical arc.

1. `rx`: it gets the proportion from it radius.

2. `ry` It increases or decreases the vertical axis respectively to the proportion provided by the `rx`

**Formula for calculating xy and xy

*Where **r** = radius, **ry**= x-axis, **ry**= y-axis, **n** = proportion value

r/ry = n

let verticalHeight = r + (n `*` (ry-rx))

**Inputing value**
r=20, ry=2, ry=3

20/2 = 10

verticalHeight = 20 + (10 * (3 - 2))

3.  `x-axis-rotation`: For rotating the circle.
4. `large-arc-flag`: A flag indicating whether to draw the larger (1) or smaller (0) arc.
5. `sweep-flag`: A flag indicating the direction of the arc (0 = clockwise, 1 = counter-clockwise).
6. `x`: The x-coordinate of the end point of the arc.
7. `y`: The y-coordinate of the end point of the arc.

These seven values work together to define the shape and orientation of the elliptical arc.

**Note**: If the `rx,ry` value exceed the radius, it pushes the eclipse downward in order to make the arc fit in.

*In order to avoid the above calculation you can make the**rx** the same with the radius and including the **ry** and then increase or decrease**ry** progressively to make the arc smaller or bigger. For example 

If the radius is 20
You should make the rx 20
Including the ry 20
And the increase or decrease the ry to make the arc smaller or bigger.
### Path S (Smooth Cubic Bezier Curve)
--- It takes two values

**S2,0 4,5**

**S2,0** : Coordinates of the second control point, why the first control is automatically controlled by svg engine.

**4,5**: is the actual line drawn.

### Path T (Smooth Quadratic Bezier Curve)
--- It takes one value

**T4,5**: This is the actual line drawn

### Path z (Close path)
--- It takes not value

It joins the endpoint and the start point together.



