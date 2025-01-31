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

is an SVG filter that changes the colors of an image, shape, or text. It works like an Instagram filter but gives you full control over how colors change.

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

