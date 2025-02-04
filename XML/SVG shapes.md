
**SVG has some predefined shape elements that can be used by developers.

1. Rectangle `<rect>
2. Circle `<circle>
3. Ellipse `<ellipse>
4. Line `<line>
5. Polyline `<polyline>
6. Polygon `<polygon>
7. Path `<path>

### rect

The `<rect>` element is used to create a rectangle and variations of a rectangle shape.

The `<rect>` element has 6 basic attributes to position and shape the rectangle:

**width** `Required`. The width of the rectangle

**height**	`Required`. The height of the rectangle

**x**	The x-position for the top-left corner of the rectangle

**y**	The y-position for the top-left corner of the rectangle

**rx**	 The x radius of the corners of the rectangle (used to round the corners). Default is 0

**ry** The y radius of the corners of the rectangle (used to round the corners). Default is 0

`<rect width="200" height="100" x="10" y="10" rx="20" ry="20" fill="blue" />`

### circle

The `<circle>` element is used to create a circle.

**r** `Required`. The radius of the circle

**cx**  The x-axis center of the circle. Default is 0

**cy**  The y-axis center of the circle. Default is 0

`<circle r="45" cx="50" cy="50" fill="red" />`

### ellipse

Element is used to create an ellipse

**rx**	`Required`. The x radius of the ellipse

**ry** `Required`. The y radius of the ellipse

**cx** The x-axis center of the ellipse. Default is 0

**cy** The y-axis center of the ellipse. Default is 0

`<ellipse rx="100" ry="50" cx="120" cy="80" />`
### line

The `<line>` element is used to create a line.

**The `<line>` element has four basic attributes to position and set the length of the line:**

**x1**	The start of the line on the x-axis

**y1**	The start of the line on the y-axis

**x2**	The end of the line on the x-axis

**y2**	The end of the line on the y-axis

`<line x1="0" y1="0" x2="300" y2="200" style="stroke:red;stroke-width:2" />`

### Polygon

Polygon comes from Greek. "Poly" means **"many"** and "gon" means **"angle"**.

The `<polygon>` element is used to create a graphic that contains at least three sides.

The `<polygon>` element has one basic attribute that defines the points of the polygon:

**points**	Required. The list of points of the polygon. Each point must contain an **x** coordinate and a **y** coordinate

`<polygon points="0,200 100,0 200,200" />`

### polyline

`<polyline>` element is used to create any shape that consists of only straight lines (that is connected at several points).

`<polyline>`  element has one basic attribute that defines the points of the polyline:

**points**	Required. The list of points of the polyline. Each point must contain an **x** coordinate and a **y** coordinates

`​<polyline points="0,0 50,150 100,75 150,50 200,140 250,140" />`