In SVG, we have four animation elements which sets or animates SVG graphics:

- `<set>`
- `<animate>`
- `<animateTransform>`
- `<animateMotion>`

### set

The `<set>` element sets the value of an attribute for a specified duration.

In this example, we create a red circle that starts with a radius of 25, then after 3 seconds the radius will be set to 50:
`<svg width="200" height="100" xmlns="http://www.w3.org/2000/svg">  <circle cx="50" cy="50" r="25" style="fill:red;">  
 `<set attributeName="r" to="50" begin="3s" />  
`</svg>

**Code explanation:**

- The `attributeName` attribute in the `<set>` element defines which attribute to change
- The `to` attribute in the `<set>` element defines the new value for the attribute
- The `begin` attribute in the `<set>` element defines when the animation should start

**Note** the shape or image you want to apply the `set` animation must not have a closing tag.


### animate

The `<animate>` element animates an attribute of an element.

The `<animate>` element should be nested inside the target element.

`<svg width="100%" height="100" xmlns="http://www.w3.org/2000/svg">  
  `<circle cx="50" cy="50" r="50" style="fill:red;">  
    `<animate      attributeName="cx"  
      begin="0s"  
      dur="8s"  
      from="50"  
      to="90%"  
      repeatCount="indefinite" />  
  `</circle>  
`</svg> `

- The `attributeName` attribute defines which attribute to animate

- The `begin` attribute defines when the animation should start

- The `dur` attribute defines the duration of the animation (How long it takes for the animation to complete per session)

- The `from` attribute defines the starting value

- The `to` attribute defines the ending value

- The `repeatCount` attribute defines how many times the animation should play (indefinite, numbers(2,5...))

- The `fill="freeze"` attribute defines that the animation should freeze when it comes to its final position

### animateTransform

` <svg viewBox="0 0 100 100" xmlns="http://www.w3.org/2000/svg">
  `<rect x="30" y="30" height="110" width="110" style="stroke:green;fill:red">
    `<animateTransform
    `attributeName="transform"
     `begin="0s"
    `dur="0.5s"
    `type="rotate"
    `from="0, 30, 30"
    `to="360 30 30"
    `repeatCount="indefinite" />
  `</rect>
`</svg> `

**Note** ensure the **X and y** coordinates in the animateTransform has the same value so as to get your expected results.

**Code explanation:**

- The `attributeName` attribute animates the `transform` attribute of the `<rect>` element
- The `begin` attribute defines when the animation should start
- The `dur` attribute defines the duration of the animation
- The `type` attribute defines the type of transformation
- The `from` attribute defines the starting value
- The `to` attribute defines the ending value
- The `repeatCount` attribute defines how many times the animation should play

### animationMotion

`<svg viewBox="0 0 100 100" xmlns="http://www.w3.org/2000/svg">
  `<rect height="20" width="20" style="stroke:green;fill:red">
    `<animateMotion
      `path="M10,20 l20,10 30,40 -50,-30 0,-20"
      `begin="0s"
      `dur="3s"
    `repeatCount="indefinite" />
  `</rect>
`</svg>`

- The `path` attribute defines the path of the animation
- The `begin` attribute defines when the animation should start
- The `dur` attribute defines the duration of the animation
- The `repeatCount` attribute defines how many times the animation should play