### **Removing an Element in JavaScript**

You can remove an element from the DOM using different methods.

#### **1. Using `remove()` (Simplest Way)**

```javascript
const element = document.querySelector("p");
element.remove(); // Removes the <p> element
```

#### **2. Using `parentNode.removeChild()` (Older Method)**

```javascript
const element = document.querySelector("p");
element.parentNode.removeChild(element); // Removes the <p> element
```

- This method is useful when you only have access to the child element.

Would you like an example where we remove multiple elements at once?