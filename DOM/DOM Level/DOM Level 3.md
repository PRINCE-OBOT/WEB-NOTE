### **Summary of DOM Level 3 (2004-2007)**

DOM Level 3 expanded on **DOM Level 2**, improving **events, document loading, XPath, validation, and keyboard interactions**.

---

### **1. Improved Event Handling**

- Introduced **mutation events** (now deprecated) to detect changes in the DOM.
- Standardized **keyboard events** (`keydown`, `keypress`, `keyup`).
    
    ```js
    document.addEventListener("keydown", function(event) {
      console.log("Key pressed:", event.key);
    });
    ```
    

---

### **2. DOM Load and Save (XML Handling)**

- Introduced APIs to **load, save, and modify XML documents** using JavaScript.
- Allowed parsing XML strings into DOM objects:
    
    ```js
    let parser = new DOMParser();
    let xmlDoc = parser.parseFromString("<note><to>User</to></note>", "text/xml");
    console.log(xmlDoc.getElementsByTagName("to")[0].textContent); // "User"
    ```
    

---

### **3. XPath Support for Advanced DOM Searching**

- Enabled searching and selecting elements using XPath expressions.
    
    ```js
    let result = document.evaluate("//div[@class='example']", document, null, XPathResult.FIRST_ORDERED_NODE_TYPE, null);
    console.log(result.singleNodeValue); // First matching div
    ```
    

---

### **4. Validation with DOM Configuration**

- Allowed **custom validation rules** for XML/HTML documents.

---

### **Key Differences from DOM Level 2**

✅ **Added `DOMParser()` and `XMLSerializer()` for XML processing.**  
✅ **Introduced XPath support for advanced element selection.**  
✅ **Improved keyboard and mutation event handling.**  
✅ **Standardized DOM validation and configuration.**  
❌ DOM Level 2 had **limited XML handling** and **no XPath support**.