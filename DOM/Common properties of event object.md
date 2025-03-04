The `event` object in JavaScript represents an event that occurs in the browser, such as a user clicking a button, pressing a key, or resizing the window. Below are some commonly used **properties** and **methods** of the event object:

### **Common Properties of `event` Object**

1. **`type`** – Returns the type of event (e.g., `"click"`, `"keydown"`, `"mouseover"`).

2. **`target`** – Returns the element that triggered the event.

3. **`currentTarget`** – Returns the element to which the event listener is attached.

4. **`bubbles`** – Returns `true` if the event bubbles up through the DOM.

5. **`cancelable`** – Returns `true` if the event is cancelable.

6. **`defaultPrevented`** – Returns `true` if the event’s default action has been prevented.

7. **`timeStamp`** – Returns the time (in milliseconds) at which the event was created.

8. **`clientX` / `clientY`** – Gets the X and Y coordinates of the mouse pointer (relative to the viewport).

9. **`pageX` / `pageY`** – Gets the X and Y coordinates of the mouse pointer (relative to the document).

10. **`key`** – Returns the key pressed in keyboard events (e.g., `"Enter"`, `"a"`, `"ArrowUp"`).

11. **`keyCode`** – Returns the numerical code of the key pressed (deprecated, use `key` instead).

12. **`altKey`**, **`ctrlKey`**, **`shiftKey`**, **`metaKey`** – Returns `true` if the corresponding key was pressed.

13. **`relatedTarget`** – In mouseover/mouseout events, returns the element the pointer came from or moved to.

### **Common Methods of `event` Object**

1. **`preventDefault()`** – Prevents the default behavior of the event (e.g., stopping form submission or link navigation).

2. **`stopPropagation()`** – Stops the event from bubbling up the DOM tree.

3. **`stopImmediatePropagation()`** – Prevents the event from being handled by other event listeners on the same element.

4. **`initEvent(type, bubbles, cancelable)`** – Initializes an event (rarely used, as modern events are created with `new Event()`).

5. **`composedPath()`** – Returns an array of elements through which the event passed.

### **Example Usage**

```javascript
document.getElementById("myButton").addEventListener("click", function(event) {
    console.log("Event Type:", event.type); // "click"
    console.log("Target Element:", event.target); // <button id="myButton">
    console.log("Mouse Coordinates:", event.clientX, event.clientY);
    event.preventDefault(); // Prevents default action if applicable
});
```
