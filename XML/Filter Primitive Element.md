### filter

Is a container element that contains the filter primitive element.

By default, the filter element in SVG has these values:

x: -10%
y: -10%
width: 120%
height: 120%

**The default width="120%" and height="120%" are relative to the bounding box of the shape or image being filtered, not the SVG viewBox.**

### feBlend 
it is used for keeping an image or shapes on top another

`<svg width="200" height="200" xmlns="http://www.w3.org/2000/svg">
  `<defs>
    `<filter id="blendFilter">
      <!-- Define two graphical inputs -->
      `<feFlood flood-color="red" result="redRect" width="100%" height="100%" />
      `<feFlood flood-color="blue" result="blueCircle" />
      `<feBlend in="redRect" in2="blueCircle" mode="multiply" />
    `</filter>
  `</defs>

  `<rect x="0" y="0" width="200" height="200" filter="url(#blendFilter)" />
`</svg>`

**feFlood**: is used to generate solid colours, and it has attributes such as;
1. **flood-color**: defines the fill color.
2. **result**: it must be provided as this is a unique identifier which will be reference to in the `feBlend (in) or (in2) attributes`.
3. **width or height**: you can further specify the height or width of the fill.

**feBlend**: blends the two *fills* on one another, using the `in` and `in2` 
1.  **in**: `id` from `feFlood` entered in the `in` at to attributes set the image or shape on top.
2. **in2**: set the images or shape backwards.
3. **mode**: such as;
     
	 1. **Normal**: It displays the color or image with it initial styles.
     
	 2. **Multiply**: *It is commonly used for darkening the `in` color*. It multiply the color of the `in2` with `in` and set it to the `in`. For example if `in2` color is red and `in` is blue i.e `rgb(255, 0, 0, 0.3)` `*` `rgb(0, 0, 255, 0.4)

   **Formula for finding multiply**
   `in * in2 / 255`

    **Application**
		**255** `*` 0 / 255 = 0
		0 `*` 0 / 255 = 0
		0 `*` 255 / 255 = 0
		0.3 `*` 0.4 = 0.12
	 
	 **Result** 
	  rgb(0, 0, 0, 0.12)


**Note**: In order to use the *Filter Element* it must be contain in the `filter` tag.

3. screen

Lightens colors by inverting them, multiplying, and inverting again.

When `in` is Black it has no effect, while white colours get brighter.

Example: Red + Blue = Light Magenta.

4. darken

Makes `in` black

5. lighten

Keeps the lighter color from in or in2.

If in is dark blue and in2 is light red, the result is light red.

6. overlay

Combines multiply and screen.

If in is dark, it uses multiply; if in is light, it uses screen.

Increases contrast.

7. color-dodge

Brightens in based on in2, reducing dark areas.

White in in2 makes in fully bright.

8. color-burn

Darkens in based on in2, increasing contrast.

Black in in2 makes in fully dark.


9. hard-light

Uses multiply for darker colors and screen for lighter colors, but applies in2 onto in.

A stronger version of overlay.


10. soft-light

Similar to hard-light, but gives a softer, more natural effect.


11. difference

Subtracts the color values of in and in2.

Identical colors turn black; different colors create high contrast.

Example: Red (RGB: 255,0,0) - Blue (RGB: 0,0,255) = Cyan (RGB: 0,255,255).


12. exclusion

Like difference, but with lower contrast.

### feColorMatrix

*It is best for **hue** and for making color **gray-scale**

is an SVG filter that changes the colors of an image. 

**Type attributes of feColorMatrix

1. **Saturate** : ==Grayscale== Effect (Black & White)
   If you want to remove colors and make the image black & white, use this: 
 
   `<feColorMatrix type="saturate" values="0"/>`

2. **matrix**: It is used for manipulating how the image, shape or text color should progressive.

   A 5×4 matrix is used to transform colors (R, G, B, Α).

   `<feColorMatrix type="matrix"
  `values="
    `a1 a2 a3 a4 a5
    `b1 b2 b3 b4 b5
    `c1 c2 c3 c4 c5
    `d1 d2 d3 d4 d5"/>`

*Each row represents how red, green, blue, and alpha is contained in that color row.*

**R1** : red
**R2**: green
**R3**: blue
**R4**: alpha

**Note**: each alpha in **rgb** defines how much light it contains, as increasing the **alpha** in each **rgb** value increases the brightness.

*Each column represents how much color each **rgba** value that will be returned.


   r         r`*`g   r`*`b     r`*`a     b  
   g`*`r    g       g`*`b    g`*`a     b 

   b`*`r    b`*`g  b         b`*`a     b

   a`*`r   a`*`g   a`*`b    a          b  
**Maximum value of rgba** -1 to 1
**Maximum value of b(brightness)** -255 to 255

**How to apply the formula**
If the shape initial color is `rgba((r)6, (g)2, (b)5, (a)1)`


#### Formula

New Red   = (R * a1) + (G * a2) + (B * a3) + (A * a4) + a5
New Green = (R * b1) + (G * b2) + (B * b3) + (A * b4) + b5
New Blue  = (R * c1) + (G * c2) + (B * c3) + (A * c4) + c5
New Alpha = (R * d1) + (G * d2) + (B * d3) + (A * d4) + d5

*Finally you then call the filtered format using*

`filter="url(#filtered)"`

### feComponentTransfer

*It is best for **brightening** or **darkening** image color*

 is used to adjust the intensity of each color channel (red, green, blue) and the alpha (opacity) of an image or shape. It allows you to manipulate how colors appear, enabling effects like brightness adjustment, contrast enhancement, and gamma correction.

`<defs>
`<filter id="brighten">
    `<feComponentTransfer>`
       //feComponentTransfer functions is contained here.
`</feComponentTransfer>
`</filter>
  `</defs>`       

**How It Works**

Inside `<feComponentTransfer>`, you define functions for each color channel using:

`<feFuncR>` – Red channel

`<feFuncG>` – Green channel

`<feFuncB>` – Blue channel

`<feFuncA>` – Alpha (opacity) channel

Each function has a type attribute to specify the transformation, like **identity**, **linear**, or **gamma**.

1. **Linear** is used if you want equal simple brightness or hue.

2. **Gamma** is used to add brightness or effects in the mid tone. (mid tone refers to colors in the image that is neither dark or light, just in between).

3. **Identity**: It keeps the color the way it is, I does not change the colour value.

4. **Table**: It is used for remapping the color in the image.

*Linear Application*

`<feFuncR type="linear" slope="0.8"/>
`<feFuncG type="linear" slope="0.8"/>
`<feFuncB type="linear" slope="1"/>`

**Linear**: ensures the colors are distributed evenly in the image.

**Slope**: define how bright or contrast the image is.


*Gamma Application*

` <feFuncR type="gamma" amplitude="1" exponent="1"/>
`<feFuncG type="gamma" amplitude="1" exponent="1"/>
`<feFuncB type="gamma" amplitude="1" exponent="1"/>`

**Amplitude** is used to make the photo appear brighter or darker. 

**Exponent** lets you fine-tune the contrast.

_______________________

**Note**: There is no fix maximum value for attributes of `feFunc.`. Value ranges between **0** and **1**

**1** : increases 
**0** : decreases 

_______________________

*Identity Application*

`<feFuncR type="identity" />`

**Identity**: do not change the value of red (unchanged).


*Table Application*

**Specifying a single value in tableValue**

`<feFuncR type="table" tableValues="0" />`


0: removes red from the image.
1 : makes the image red, even the dark part of the image becomes bright red.

**Specifying two value in tableValue**

`<feFuncR type="table" tableValues="0 1" />`

**first parameter** keep dark unchanged 
**second parameter** keep red unchanged

### feGaussianBlur

It's used to blur image

`<feGaussianBlur in="SourceGraphic" stdDeviation="0" />`

**in**: defines the image that takes the blur.  In this case it is the image that has the `filter id`

**stdDeviation**: defines how blurry the image will be.

**Default value** 0
As the value increases the blur increases.

**Applying feBlend together with blur**

`<feGaussianBlur stdDeviation="1" />`

`<feBlend in="SourceGraphic" mode"multiply" />`

### feFlood 
It is used to create solid colour.
`<filter id="solid-color" >`
    `<feFlood flood-color="red" />`
`</filter>`

` <rect x="0" y="0" width="50%" height="50%" filter="url(#solid-color)" />`

### feImage

It is best used if you want to blend images together using `feBlend` otherwise use `image`.

`<feImage x="" y="" width="100%" height="100%" href="./pic.jpg" />`

###   feOffset 

It is used to shift an image or shape.

*Positive **dx** value shift the shape from the left, negative **dx** value shift the shape from the right.*

*Positive **dy** value shift the shape from the top, negative **dy** value shift the shape from bottom.

`<feOffset in="SourceGraphic" dx="40" dy="40"/>`

`feOffset in="SourceAlpha" dx="40" dy="40"/>`

### feMerge 

It gives you a chance to used multiple filter together.

It is used to combine multiple filter effects into one. 

`<svg width="200" height="200">
  `<defs>
    `<filter id="mergeFilter">
      `<feOffset in="SourceAlpha" dx="5" dy="5" result="offsetEffect"/>
     `<feGaussianBlur in="offsetEffect" stdDeviation="2" result="blurEffect"/>
      `<feMerge>
        `<feMergeNode in="blurEffect"/>
        `<feMergeNode in="SourceGraphic"/>
      `</feMerge>
   `</filter>
  `</defs>

  `<rect x="50" y="50" width="100" height="100" fill="blue" filter="url(#mergeFilter)"/>
`</svg>`

*The process proceed in order. First the **feOffSet** is defined, contained with the **result** attributes which the at as a reference for the **feGassiunBlur** to apply the blur, which also contained the **result** attributes which is later referenced by the **feMerge**.

The **feMerge** has two attributes. From the code the first `in` is the cloned shape that has pass through process of `feOffset` and `feGassiunBlur` the second `in` is the shape that the style will be applied to.

The order the `feMergeNode` is arrange in `feMerge` determine which will be in front, either the clone version or the original version.