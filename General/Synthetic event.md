A **synthetic event** is an event that is **not triggered directly by user interaction** but is instead **generated by the browser or JavaScript**.

### **Types of Synthetic Events**

1. **Browser-Generated Events**
    
    - Some browsers **automatically** trigger certain events under specific conditions.
    - Example:
        - When you focus on an element using the `Tab` key, some browsers fire a **synthetic `click`** on the previously focused element.
        - When you submit a form by pressing `Enter`, a synthetic `submit` event may be fired.
2. **JavaScript-Generated Events**
    
    - You can manually create and dispatch events using JavaScript.
    - Example:
        
        ```javascript

const event = new Event("click"); // Create a synthetic click event

const btn = document.querySelector("button")
        
btn.addEventListener('click')      
btn.dispatchEvent(event); // Fire the event
        ```
        
    - This will make it **look like** the button was clicked, even though the user didn’t actually click it.

### **How to Detect Synthetic Events?**

- **For browser-generated synthetic clicks:**  
    Use `event.detail === 0`, because real mouse clicks have `event.detail` **1 or greater**.
    
    ```javascript
    document.addEventListener("click", (e) => {
        if (e.detail === 0) {
            console.log("Synthetic click detected!");
        } else {
            console.log("Real click detected!");
        }
    });
    ```
    
- **For JavaScript-triggered events:**  
    You can check if `isTrusted` is `false`.
    
    ```javascript
    document.addEventListener("click", (e) => {
        console.log(e.isTrusted ? "Real user action" : "Synthetic event");
    });
    
    // Trigger a synthetic event
    document.body.dispatchEvent(new Event("click"));
    ```
    
    - `e.isTrusted === true` → Real user interaction.
    - `e.isTrusted === false` → Synthetic (programmatically created) event.

### **Final Thoughts**

Synthetic events can be useful, but they can also cause unexpected behavior, like your case where `click` fired on `.con` when focusing on `.child`. Filtering out synthetic clicks (`event.detail === 0`) helps prevent that issue.

Let me know if you need more clarification!