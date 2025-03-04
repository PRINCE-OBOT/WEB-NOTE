Here’s a structured and **consistent** list of browser default behaviors that `preventDefault()` can stop:

---

## **1. Mouse Events**

These events trigger default behaviors in the browser.

### **Right-click context menu**

```js
document.addEventListener("contextmenu", (e) => {
    e.preventDefault(); // Disables the right-click menu
});
```

### **Text selection (via double-click or drag)**

```js
document.addEventListener("selectstart", (e) => {
    e.preventDefault(); // Prevents text selection
});

//Or but this does it indirectly, because mousedown is the first stage, so when prevent stops the chain from reaching selectstart.

document.addEventListener("mousedown", (e) => {
    e.preventDefault(); // Prevents text selection
});
```

### **Dragging elements (default behavior for images and links)**

```js
document.addEventListener("dragstart", (e) => {
    e.preventDefault(); // Stops images, links, and text from being dragged
});
```

### **Middle-click to open links in a new tab**

```js
document.addEventListener("auxclick", (e) => {
    if (e.button === 1) { // Middle mouse button
        e.preventDefault(); // Stops opening links in a new tab
    }
});
```

---

## **2. Keyboard Events**

Some keys have built-in browser behaviors.

### **Prevent spacebar from scrolling the page**

```js
document.addEventListener("keydown", (e) => {
    if (e.key === " ") {
        e.preventDefault(); // Stops spacebar from scrolling
    }
});
```

### **Prevent backspace from navigating back**

```js
document.addEventListener("keydown", (e) => {
    if (e.key === "Backspace") {
        e.preventDefault(); // Stops Backspace from navigating back
    }
});
```

---

## **3. Form Events**

Forms have behaviors that can be prevented.

### **Prevent form submission**

```js
document.querySelector("form").addEventListener("submit", (e) => {
    e.preventDefault(); // Stops the form from submitting
});
```

### **Prevent Enter key from submitting a form**

```js
document.addEventListener("keydown", (e) => {
    if (e.key === "Enter") {
        e.preventDefault(); // Stops Enter from submitting a form
    }
});
```

---

## **4. Scroll Events**

Some events trigger scrolling by default.

### **Prevent mouse wheel from scrolling the page**

```js
document.addEventListener("wheel", (e) => {
    e.preventDefault(); // Stops page scrolling with mouse wheel
}, { passive: false });
```

### **Prevent touch scrolling (on mobile devices)**

```js
document.addEventListener("touchmove", (e) => {
    e.preventDefault(); // Stops touch scrolling
}, { passive: false });
```

---

## **5. Drag & Drop Events**

By default, some elements allow dragging.

### **Prevent elements from being dragged**

```js
document.addEventListener("dragover", (e) => {
    e.preventDefault(); // Allows dropping instead of default browser behavior
});
```

---

## **6. Clipboard Events**

Browsers allow copying and pasting by default.

### **Prevent text from being copied**

```js
document.addEventListener("copy", (e) => {
    e.preventDefault(); // Stops text from being copied
});
```

### **Prevent text from being cut**

```js
document.addEventListener("cut", (e) => {
    e.preventDefault(); // Stops text from being cut
});
```

### **Prevent text from being pasted**

```js
document.addEventListener("paste", (e) => {
    e.preventDefault(); // Stops pasting
});
```

---

## **7. Focus & Blur Events**

Some elements like input fields and links have built-in focus behaviors.

### **Prevent input from gaining focus (not possible with preventDefault)**

```js
document.getElementById("input").addEventListener("focus", (e) => {
    e.preventDefault(); // ❌ Does nothing because focus is not cancelable
});
```

> **Note:** `focus` and `blur` are **not cancelable** events, so `preventDefault()` does **not** work here.

---

## **8. Media Events**

Some media elements have default behaviors.

### **Prevent a video from playing (not possible with preventDefault)**

```js
document.querySelector("video").addEventListener("play", (e) => {
    e.preventDefault(); // ❌ Does nothing because play is not cancelable
});
```

> **Note:** `play` and `pause` **are not cancelable**, so `preventDefault()` does nothing.

---

## **9. Navigation Events**

Browsers have built-in navigation behaviors.

### **Prevent clicking a link from navigating to a new page**

```js
document.querySelector("a").addEventListener("click", (e) => {
    e.preventDefault(); // Stops the link from navigating
});
```

---

## **Key Takeaways**

1. **`preventDefault()` only works on events that have default browser behaviors.**
2. **Some events (e.g., `focus`, `play`) cannot be prevented because they are not cancelable.**
3. **Manually dispatched events (`dispatchEvent()`) do not have default behaviors, so `preventDefault()` does nothing on them.**
4. **If an event supports `preventDefault()`,** `event.cancelable` **will be `true`.**

Would you like me to add anything else?