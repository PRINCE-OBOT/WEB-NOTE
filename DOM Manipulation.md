# Keyboard Events

These are events that occur when the keyboard is been pressed
##Three main keyboard events
**keydown:** fires as long as the keyboard is been held.
**keyup:** fires when the keyboard is release.
**keypress:** fires as long as the keyboard is been held.

## Two main properties of keyboard events

**key**: display the key press

**code**: displays "key" with the key pressed. e.g if key "G" is pressed it displays like (keyG)

**Note:** keydown and keypress continues to fire as long as the keyboard is been held
keydown and keyup provides keyboard property information for all keys whereas keypress provide information for the keyboard characters i.e a, b, ...z & 0, 1, 2 ...9

# Event Constructors

It is use to fire event without using the regular mouse click and keyboard event
Event constructors accept two parameters
**type**: specify the type of event
**options**: is an object with two optional properties (bubbles, cancelable - and they are false by default)
**bubbles**: if set to `true` the parent container is been fired else false
**cancelable**: if set to `true` the default behavior of the element can be prevented using `preventDefault()`. e.g (if anchor `a` is connected with an event constructor, setting the property object of `cancelable: true` allows `preventDefault()` to be effective in `a`)
The code below fires without having to use the regular events.

`e.isTrusted` returns `true` if user perform the action using mouse click or keyboard event, but if generated by Event Constructors it is `false`

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
`    const btn = document.querySelector(".btn");
      btn.addEventListener("click", (e) => {
        console.log(`${e.screenX}, ${e.screenY}`);
      });
      let myEvent = new MouseEvent("click", {
        bubble : true,
        cancelable: true,
        screenX: undefined,
        screenY: undefined
        clientX: undefined,
        clientY: undefined,
        offsetX: undefined,
        offsetY: undefined,
        pageX: undefined, 
        pageY: undefined
      });
      btn.dispatchEvent(myEvent);
`

## KeyboardEvent Properties (Application in Event Constructors)

`    const input = document.querySelector(".input");
      input.addEventListener("keydown", (e) => {
        console.log(`${e.key}, ${e.code}`);
      });
      let myEvent = new KeyboardEvent("keydown", {
        bubble : true,
        cancelable: true
        key:enter,
        code:enter,
      });
      input.dispatchEvent(myEvent);
`