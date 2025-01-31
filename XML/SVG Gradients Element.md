It is used to generate smooth transition of colours in a shape.

### Linear Gradient 

**Note**: linear gradient property always exist inside of a `defs` element.

`<defs>`
` <linearGradient id="gradient" x1="50%" y1="0%" x2="50%" y2="100%">`
     `<stop offset="0%" stop-color="red">`
` </linearGradient> `
`</defs>
`<rect fill="url(#gradient)" rx="10" ry="10" width="100" height="100" />`

**id**: References the linear-gradient 

**x1,y1**: This is the starting point, **x2,y2**: This is the ending point. (It is used for orientating the linear-gradient color, more like `rotate(deg)`).

**defs** : it is the container and more like an existing place for linear-gradient property.

**stop** : specify the position of the color and color the color itself.


### Radial gradient 

`<defs>`
` <radialGradient id="gradient" cx="30%" cy="0%" r="20%" fx="40%" fy="10%">`
     `<stop offset="0%" stop-color="red">`
` </radialGradient> `
`</defs>
`<rect fill="url(#gradient)" rx="10" ry="10" width="100" height="100" />`

**id**: References the linear-gradient 

**cx, cy**: This provide the pivot point for the radial-gradient to start from.

**r**: It is used to determine the size of the radial-gradient.

**fx, fy**: It is used to adjust the radial-gradient color itself.

**Note**: if `fx` and `fy` is not specified it takes the value of `cx` and `cy`




