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

The **Q8,2**
The first **Q8**  set the curve for the x-axis. Pushes the curve further away from the line by 8 unit.

The **Q2** set the curve for the y - axis. Pushes the curve further into the line by 2 unit.

The **8,8** specify how long the line length will be, which is *8*.

And the second 8 specify how further away it is from the y - axis.

### Path C (M2,2 C2,8 0,9 8,2) - CUBIC BEZIER CURVE 

**--- It has 3 value**
**The cubic bezier curve***

 **C2,8**- This provide a means for the slope to pass through. **2** : means 2 unit away from the x-axis.  **8** : means 8 unit away from the y-axis.

**0,9**: Pushes the slope point away. **0** pushes it horizontally, **9** pushes it vertically.

**8,2**: It is the actual line drawn, **8** draws a line of 8 unit long, **5** pushes the endpoint away away from the top by 5 units.

### Path A (Elliptical arc)
--- It has 7 values 
The `A` attribute in the `<path>` 
element of SVG is used to draw an elliptical arc.

1. `rx`: The horizontal radius of the ellipse. (How in depth the arc should be)
2. `ry`: The vertical radius of the ellipse. (Pushes the slope inside vertically)
3. `x-axis-rotation`: The rotation of the ellipse around the x-axis (Pushes the slope horizontally).
4. `large-arc-flag`: A flag indicating whether to draw the larger (1) or smaller (0) arc.
5. `sweep-flag`: A flag indicating the direction of the arc (0 = clockwise, 1 = counter-clockwise).
6. `x`: The x-coordinate of the end point of the arc.
7. `y`: The y-coordinate of the end point of the arc.

These seven values work together to define the shape and orientation of the elliptical arc.

### Path S (Smooth Cubic Bezier Curve)
--- It takes two values

**S2,0 4,5**

**S2,0** : Defines how long the slope is and away from the x-axis

**2**: pushes the slope 2 unit away from the x-axis.
**0**: Tells how long the middle is away from the start and endpoint.

**4,5**: is the actual line drawn.

### Path T (Smooth Quadratic Bezier Curve)
--- It takes one value

**T4,5**: This is the actual line drawn

### Path z (Close path)
--- It takes not value

It joins the endpoint and the start point together.



