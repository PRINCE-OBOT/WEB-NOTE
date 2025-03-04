In JavaScript, **event bubbling** and **event capturing** are two event propagation models that determine how events travel through the DOM when an event is triggered.

## **1. Event Bubbling**

Event bubbling happens when an event starts from the **target element** (the element that was clicked or interacted with) and propagates **upward** through its ancestors in the DOM tree.

### **How it Works**

- When an event occurs on a child element, it first triggers that element’s event handler.
- Then, it moves up to the parent element, triggering its event handlers (if any).
- The process continues up to the `<html>` element.

### **Example**

```javascript
document.getElementById("child").addEventListener("click", function () {
    console.log("Child clicked");
});

document.getElementById("parent").addEventListener("click", function () {
    console.log("Parent clicked");
});

document.getElementById("grandparent").addEventListener("click", function () {
    console.log("Grandparent clicked");
});
```

**If you click on `child`, the output will be:**

```
Child clicked
Parent clicked
Grandparent clicked
```

The event "bubbles" up from `child` → `parent` → `grandparent`.

---

## **2. Event Capturing (Event Trickling)**

Event capturing is the **opposite** of bubbling. The event starts at the **topmost ancestor** and moves **downward** to the target element.

### **How it Works**

- The event first triggers on the outermost parent element.
- Then, it moves down to the child elements until it reaches the target element.

### **Example**

To enable capturing, we pass `true` as the third argument in `addEventListener`:

```javascript
document.getElementById("grandparent").addEventListener("click", function () {
    console.log("Grandparent clicked");
}, true);

document.getElementById("parent").addEventListener("click", function () {
    console.log("Parent clicked");
}, true);

document.getElementById("child").addEventListener("click", function () {
    console.log("Child clicked");
}, true);
```

**If you click on `child`, the output will be:**

```
Grandparent clicked
Parent clicked
Child clicked
```

The event "trickles" down from `grandparent` → `parent` → `child`.

---

## **Key Differences**

Would you like a practical exercise to reinforce this?