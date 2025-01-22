*If you forget how hinge looks, browse the photo*

It is use to determine the point, where the hinge is fixed, So that the `transform` value are not limited to been modified from the middle.

**Example**: 
`div {
  `width: 100px;
  `height: 100px;
  `padding: 10px;
  `border: 5px solid black;
  `margin: 20px;
  `transform: rotate(45deg);
  `transform-origin: 50% 50%;
`}

By default transform-origin is 50% 50%...
**How is it calculated?** 

It is calculated using the Border-box measurement.
*What to know about border box: it ensures that the padding and border **units** is removed from the **width** and **height**

From the CSS code above, that means the Border box measurement for the width is **120px** ( width:100 + margin:20) Not including **border** as it has been removed from the width 

And the border box measurement for the height is **120px** (height: 100 + margin: 20 ) Not including **border** as it has been removed from the width 

Calculating the `transform-origin of 50% 50%`

`x and y` respectively. x(width), y(height)

Width 50% of 120 = 60
Height 50% of 120 = 60

The hinge is been place in the middle of the element, making it to been modify from the middle.

