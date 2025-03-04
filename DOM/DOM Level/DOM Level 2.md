### **Implemented Year (2000)**

DOM Level 2 expanded on **DOM Level 1**, introducing **better event handling, CSS manipulation, and document traversal**.

---

### **1. Advanced Event Handling (Event Flow Introduced)**

- Introduced **event flow with three phases**:
    1. **Capturing Phase** → Event moves from the document down to the target.
    2. **Target Phase** → Event fires on the target element.
    3. **Bubbling Phase** → Event moves back up to the root.
- Added `addEventListener()` for **multiple event handlers per element** and phase control.
    
    ```js
    element.addEventListener("click", myFunction, true); // Capturing  
    element.addEventListener("click", myFunction, false); // Bubbling  
    ```
    
- Allowed developers to **stop event propagation** (`stopPropagation()`).

---

### **2. Event Delegation Becomes Possible**

- Since events bubble up, a single parent can handle events for multiple child elements.
    
    ```js
    document.getElementById("parent").addEventListener("click", function(event) {
      if (event.target.matches(".child")) {
        alert("Child Clicked!");
      }
    });
    ```
    
- No need to attach events to every child element manually.

---

### **3. Better CSS Control**

- Introduced the **CSS Object Model (CSSOM)** for dynamic stylesheet manipulation.
- Allowed accessing and modifying stylesheets dynamically:
    
    ```js
    document.styleSheets[0].cssRules[0].style.color = "red";
    ```
    

---

### **4. Enhanced Document Traversal**

- Added the **Traversal and Range API** for navigating the DOM more efficiently.
- Example:
    
    ```js
    let firstChild = document.getElementById("parent").firstChild;
    console.log(firstChild.nodeName);
    ```
    

---

### **5. XML and Namespaces Support**

- Introduced support for **XML namespaces**, making the DOM more compatible with XML documents.

---

### **Key Differences from DOM Level 1**

✅ **Full event flow control** (capturing, target, bubbling).  
✅ **Multiple event listeners per element (`addEventListener()`).**  
✅ **Event delegation support.**  
✅ **Improved document traversal and CSS control.**  
❌ DOM Level 1 lacked event flow and had only inline event handling.

Would you like a summary of DOM Level 3 next?