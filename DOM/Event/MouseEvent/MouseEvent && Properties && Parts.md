**Note**`mousedown` and `mouseup` fires when any button is pressed.

1. mousedown – Fires when a mouse button is pressed down over an element.


2. mouseup – Fires when a pressed mouse button is released.


3. click – Fires when a mouse button is pressed and released on an element (combination of mousedown and mouseup).


4. dblclick – Fires when the mouse is clicked twice in rapid succession.


5. mousemove – Fires whenever the mouse moves over an element.


6. mouseenter – Fires when the mouse enters an element's area (does not bubble).


7. mouseleave – Fires when the mouse leaves an element's area (does not bubble).


8. mouseover – Fires when the mouse enters an element or its child elements (bubbles).


9. mouseout – Fires when the mouse leaves an element or its child elements (bubbles).


10. contextmenu – Fires when the right mouse button is clicked, typically opening the context menu.
## MouseEvent Properties (Application in Event Constructors)

### client

This is the feasible region around the webpage (plain white default webpage), excluding the window, navigation bar
Note: If the webpage is shrink or resized the clientX or clientY views automatically adapt to the webpage feasible region.

### screen

This is the provide measurement from the point a mouse is click, starting from the edge of the device screen (It is the entire viewport of your device)

### offset

Provide measurement of "container|single element" from border of the element to the position is was clicked

### page

Similar with client as it provide measurement of the webpage position clicked, but this time it does not base on the feasible region (i.e if the webpage is scrollable it measures through it)
**X** represent the horizontal position of the mouse pointer.
**Y** represent the vertical axis of the the mouse pointer.

## Part of mouse

- **Left Button** → `0`
- **Middle Button (Scroll Wheel Click)** → `1`
- **Right Button** → `2`
- **Back Button (Browser Back)** → `3`
- **Forward Button (Browser Forward)** → `4`

You can detect these using the **event.button** property in a `mousedown` or `mouseup` event.

Would you like a quick example of detecting mouse button clicks?