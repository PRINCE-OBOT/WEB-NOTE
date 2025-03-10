Alright! Let’s break it down in a way that makes sense.

### **1. `DOMContentLoaded`**

- This event fires **as soon as the HTML is fully loaded and parsed**, but before stylesheets, images, and other external resources finish loading.
- If you want to manipulate the DOM (change text, add elements, etc.), this is the best event to use.

**Example:**

```javascript
document.addEventListener("DOMContentLoaded", function () {
    console.log("DOM is ready, but images and CSS may still be loading.");
});
```

Think of it like: **"The structure of the house is ready, but furniture is still being placed."**

---

### **2. `load`**

- Fires when **everything** on the page has fully loaded—including images, CSS, and scripts.
- Use this event if you need **everything** to be ready before executing code.

**Example:**

```javascript
window.addEventListener("load", function () {
    console.log("Everything is fully loaded, including images and styles.");
});
```

Imagine: **"The house is completely furnished and ready to live in."**

---

### **3. `beforeunload`**

- This event fires **just before the user leaves the page** (closing tab, refreshing, navigating away).
- It’s often used to **warn users** if they have unsaved changes.

**Example:**

```

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Beforeunload Test</title>
    <script>
        let isFormDirty = false; // Track changes

        // Detect input changes
        document.addEventListener("input", function () {
            isFormDirty = true;
        });

        window.addEventListener("beforeunload", function (event) {
            if (isFormDirty) {
                event.preventDefault();
                event.returnValue = ""; // Triggers browser warning
            }
        });
    </script>
</head>
<body>
    <h1>Try leaving after typing something</h1>
    <input type="text" placeholder="Type something..." />
</body>
</html>
```

Think of it as: **"Wait! Are you sure you want to exit?"**

---

### **4. `unload`**

- Fires **after** the user has already left the page.
- Used for cleanup (e.g., saving data to a server, stopping background tasks).

**Example:**

```javascript
.   window.addEventListener("unload", function () {
    navigator.sendBeacon("https://webhook.site/3297676d-5bdc-4b7c-adb8-29c2ade37b60", data); 
//send message to webhook site when user exit page.
//This is a substitute for sending request to server.
});
```

This is like: **"The house is now empty; time to turn off the lights."**

---

### **How They Work in Order**

1. `DOMContentLoaded` → **HTML is loaded and ready.**
2. `load` → **Everything (images, CSS) is fully loaded.**
3. `beforeunload` → **User is about to leave.**
4. `unload` → **User has left the page.**

---

### 5. **`readystatechange`** 

The **`readystatechange`** event is a built-in event in JavaScript that fires whenever the **`document.readyState`** property changes. It helps track different stages of a webpage’s loading process.

### How It Works

The browser updates **`document.readyState`** as the page loads, going through these phases:

1. **`loading`** – The HTML is still being loaded and parsed. The DOM is not ready yet.
2. **`interactive`** – The HTML is fully loaded, and the DOM is ready, but images, CSS, and sub-resources may still be loading.
3. **`complete`** – Everything, including images and CSS, has fully loaded.

### Example

```javascript
document.addEventListener('readystatechange', () => {
  console.log(`ReadyState: ${document.readyState}`);
  
  if (document.readyState === 'interactive') {
    console.log('DOM is ready but images and styles may still be loading.');
  }

  if (document.readyState === 'complete') {
    console.log('Everything is fully loaded.');
  }
});
```

### When to Use `readystatechange`

- If you need to execute code **as soon as the DOM is ready** (before images/styles are loaded), check for `"interactive"`.
- If you want to know **when everything is fully loaded**, checking for `"complete"` is similar to using the **`load`** event.

However, the **`load`** event is usually more reliable for ensuring that all resources are 100% loaded.