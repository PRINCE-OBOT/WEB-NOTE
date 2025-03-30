

### **1. Window Events**

- `beforeunload` – Fires when the user is about to leave the page.
- `visibilitychange` – Fires when the page visibility changes (e.g., switching tabs).
- `online` – Fires when the internet connection is restored.
- `offline` – Fires when the internet connection is lost.
- `pagehide` – Fires when the page is hidden (e.g., navigating away).
- `pageshow` – Fires when the page becomes visible again.
- `resize` – Fires when the browser window is resized.
- `scroll` – Fires when an element or the page is scrolled.

### **2. Clipboard Events**

- `copy` – Fires when content is copied.
- `cut` – Fires when content is cut.
- `paste` – Fires when content is pasted.

### **3. Mouse & Pointer Events**

- `click` – Fires when an element is clicked.
- `dblclick` – Fires when an element is double-clicked.
- `mousedown` – Fires when a mouse button is pressed.
- `mouseup` – Fires when a mouse button is released.
- `mousemove` – Fires when the mouse moves.
- `mouseenter` – Fires when the mouse enters an element (does not bubble).
- `mouseleave` – Fires when the mouse leaves an element (does not bubble).
- `mouseover` – Fires when the mouse enters an element or its child.
- `mouseout` – Fires when the mouse leaves an element or its child.
- `contextmenu` – Fires when the user right-clicks.
- `wheel` – Fires when the user scrolls using the mouse wheel.
- `pointerdown` – Fires when any pointer (mouse, touch, stylus) is pressed.
- `pointerup` – Fires when a pointer is released.
- `pointermove` – Fires when a pointer moves.
- `pointerenter` – Fires when a pointer enters an element (similar to `mouseenter`).
- `pointerleave` – Fires when a pointer leaves an element (similar to `mouseleave`).
- `pointerover` – Fires when a pointer enters an element or its child.
- `pointerout` – Fires when a pointer leaves an element or its child.

### **4. Drag & Drop Events**

- `drag` – Fires continuously while dragging an element.
- `dragstart` – Fires when dragging starts.
- `dragend` – Fires when dragging ends.
- `dragenter` – Fires when a dragged element enters a drop target.
- `dragleave` – Fires when a dragged element leaves a drop target.
- `dragover` – Fires when a dragged element is over a drop target.
- `drop` – Fires when a dragged element is dropped on a valid target.

### **5. Keyboard & Input Events**

- `keydown` – Fires when a key is pressed down.
- `keyup` – Fires when a key is released.
- `keypress` – **Deprecated**, use `keydown` or `keyup` instead.
- `input` – Fires when an input field’s value changes.
- `change` – Fires when an input element loses focus after changing.
- `focus` – Fires when an element gains focus.
- `blur` – Fires when an element loses focus.
- `focusin` – Similar to `focus`, but bubbles up.
- `focusout` – Similar to `blur`, but bubbles up.

### **6. Form Events**

- `submit` – Fires when a form is submitted.
- `reset` – Fires when a form is reset.
- `invalid` – Fires when an input fails validation.

### **7. CSS Animation & Transition Events**

- `animationstart` – Fires when a CSS animation starts.
- `animationend` – Fires when a CSS animation ends.
- `animationiteration` – Fires when a CSS animation repeats.
- `transitionend` – Fires when a CSS transition completes.

### **8. Touch Events (For Mobile Devices)**

- `touchstart` – Fires when a touch starts on an element.
- `touchmove` – Fires when a touch moves on an element.
- `touchend` – Fires when a touch ends on an element.
- `touchcancel` – Fires when a touch is interrupted (e.g., switching tabs).

### **9. Media Events**

- `play` – Fires when media (audio/video) starts playing.
- `pause` – Fires when media is paused.
- `ended` – Fires when media reaches the end.
- `timeupdate` – Fires when media playback position changes.
- `volumechange` – Fires when volume is changed.
- `canplay` – Fires when media can start playing without buffering.
- `waiting` – Fires when media is buffering.

### **10. Storage Events**

- `storage` – Fires when `localStorage` or `sessionStorage` is updated in another tab.

