It is used to generate smooth transition of colours in a shape.

### Linear Gradient 

|                   |                                                                                                                                             |
| ----------------- | ------------------------------------------------------------------------------------------------------------------------------------------- |
| id                | Required. Defines a unique id for the <linearGradient> element                                                                              |
| x1                | The x position of the starting point of the vector gradient. Default is 0%                                                                  |
| x2                | The x position of the ending point of the vector gradient. Default is 100%                                                                  |
| y1                | The y position of the starting point of the vector gradient. Default is 0%                                                                  |
| y2                | The y position of the ending point of the vector gradient. Default is 0%                                                                    |
| spreadMethod      | Defines the spread method of the gradient. Possible values: "pad", "reflect", "repeat". Default is "pad"                                    |
| href              | Defines a reference to another <linearGradient> element that will be used as a template                                                     |
| gradientUnits     | Defines the coordinate system for x1, x2, y1, y2. Possible values: "userSpaceOnUse" and "objectBoundingBox". Default is "objectBoundingBox" |
| gradientTransform | Defines additional transformation to the gradient coordinate system                                                                         |
**Note**: linear gradient property always exist inside of a `defs` element.

`<defs>`
` <linearGradient id="gradient" x1="50%" y1="0%" x2="50%" y2="100%">`
     `<stop offset="0%" stop-color="red">`
` </linearGradient> `
` <linearGradient id="linear2" href="#linear"> 
  `<stop />`
`</linearGradient>`
`</defs>
`<rect fill="url(#gradient)" rx="10" ry="10" width="100" height="100" />`

**id**: References the linear-gradient 

**x1,y1**: This is the starting point, **x2,y2**: This is the ending point. (It is used for orientating the linear-gradient color, more like `rotate(deg)`).

**defs** : it is the container and more like an existing place for linear-gradient property.

**stop** : specify the position of the color and color the color itself.

**href** : references the property of other linear gradient.

### Radial gradient 

| Attribute         | Description                                                                                                                                                                                         |
| ----------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| id                | Required. Defines a unique id for the <radialGradient> element                                                                                                                                      |
| cx                | The x position of the end circle of the radial gradient. Default is 50%                                                                                                                             |
| cy                | The y position of the end circle of the radial gradient. Default is 50%                                                                                                                             |
| fr                | The radius of the start circle of the radial gradient. Default is 0%                                                                                                                                |
| fx                | The x position of the start circle of the radial gradient. Default is 50%                                                                                                                           |
| fy                | The y position of the start circle of the radial gradient. Default is 50%                                                                                                                           |
| r                 | The radius of the end circle of the radial gradient. Default is 50%                                                                                                                                 |
| spreadMethod      | Defines the spread method of the gradient. Possible values: "pad", "reflect", "repeat". Default is "pad"                                                                                            |
| href              | Defines a reference to another <radialGradient> element that will be used as a template                                                                                                             |
| gradientUnits     | Defines the coordinate system for cx, cy, r, fx, fy, fr. Possible values: "userSpaceOnUse" (absolute to the SVG)and "objectBoundingBox" (Relative to the container). Default is "objectBoundingBox" |
| gradientTransform | Defines additional transformation to the gradient coordinate system                                                                                                                                 |

`<defs>`
` <radialGradient id="gradient" cx="30%" cy="0%" r="20%" fx="40%" fy="10%">`
     `<stop offset="0%" stop-color="red">`
` </radialGradient> `
`</defs>
`<rect fill="url(#gradient)" rx="10" ry="10" width="100" height="100" />`

**id**: References the linear-gradient 

**cx, cy**: This provide the pivot point for the radial-gradient to start from (Move the entire color excluding the last `offset` color).

**r**: It is used to determine the size of the radial-gradient.

**fx, fy**: It is used to adjust the radial-gradient color itself. (It moves the color from the middle)

**Note**: if `fx` and `fy` is not specified it takes the value of `cx` and `cy`




