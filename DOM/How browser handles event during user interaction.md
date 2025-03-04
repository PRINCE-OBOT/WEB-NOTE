
When a user performs an action—such as **clicking, focusing, or pressing a key**—the browser detects multiple events that may be triggered by that single action. For example, when a user **clicks**, the browser registers not only the `click` event but also related events like `mousedown` (when the button is pressed) and `mouseup` (when the button is released).

#### **Example**

A **click event** consists of both **pressing** and **releasing** the mouse, which is also true for a **focus event** (if the clicked element is focusable).

#### **How Events Are Processed**

When an action occurs, the browser detects all the possible events associated with it and **dispatches them in order**. It is then up to the event listeners to determine whether they should respond to any of these events.

#### **Code Example**

```html
<div class="con">Father
  <div class="child" tabindex="0">Child</div>
</div>
```

```javascript
const con = document.querySelector('.con');
const child = document.querySelector('.child');

con.addEventListener('click', (e) => {
    alert('con');
});

child.addEventListener('focus', (e) => {
    alert('child');
});
```

### **Why Does the Parent Fire When Focus Doesn’t Bubble?**

The `focus` event **does not bubble**, meaning it doesn't propagate up the DOM. However, when the child receives focus (for example, by clicking on it), the browser also detects the `click` event, which **does bubble**.

Since the `click` event is part of the list of possible actions the browser detected, and the parent (`.con`) has a listener for `click`, the event propagates up and triggers the listener on the parent.

### **Conclusion**

- The browser detects all relevant events from a user action and queues them.
- Event listeners only respond if they match one of these events.
- Even though `focus` doesn’t bubble, the `click` event does, which is why the parent’s listener gets triggered when clicking on a focusable child.

---
