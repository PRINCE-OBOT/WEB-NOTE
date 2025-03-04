

### **1. `innerHTML` (HTML Content Manipulation)**

- They are used in displaying content on the webpage, and they understands HTML tags. 

**Example:**

```javascript
const element = document.querySelector("div");
element.innerHTML = "<strong>Bold Text</strong>"; // Inserts HTML
console.log(element.innerHTML); // Outputs: <strong>Bold Text</strong>
```

✔️ Use when working with **HTML inside an element**.  
❌ Security risk if using user input (can lead to XSS attacks).

---

### **2. `innerText` (Visible Text Only)**

- It displays the text as it is formatted in the HTML, keeps the (space, breaking line, and display : none, if set).

**Example:**

```javascript
const element = document.querySelector("div");
element.innerText = "Bold Text"; // Treats as plain text
console.log(element.innerText); // Outputs: <strong>Bold Text</strong>
```

✔️ Ignores hidden elements and respects CSS styles.  
❌ Slower than `textContent` because it checks styles.

---

### **3. `textContent` (Raw Text, Including Hidden Content)**

- Retrieves or sets the **raw text content**, including hidden elements.
- Doesn’t process HTML, treats everything as text.

**Example:**

```javascript
const element = document.querySelector("div");
element.textContent = "Bold Text"; // Treats as plain text
console.log(element.textContent); // Outputs: <strong>Bold Text</strong>
```

✔️ Fastest and most secure option for retrieving text.  
❌ Doesn’t ignore hidden elements like `innerText` does.

---

### **Comparison Table**

#### **When to Use What?**

- ✅ **Use `innerHTML`** when working with HTML elements inside an element.
- ✅ **Use `innerText`** when you need only **visible** text.
- ✅ **Use `textContent`** when you need all text, including hidden content.