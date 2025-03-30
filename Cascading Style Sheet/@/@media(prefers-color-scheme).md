

### **`prefers-color-scheme` Media Query**

The `prefers-color-scheme` media query detects whether the user has set their system to **light mode** or **dark mode** and applies styles accordingly.

### **Syntax:**

```css
@media (prefers-color-scheme: dark) {
  body {
    background: black;
    color: white;
  }
}
```

- This applies styles only when the system is in **dark mode**.
    

```css
@media (prefers-color-scheme: light) {
  body {
    background: white;
    color: black;
  }
}
```

- This applies styles when the system is in **light mode**.
    

### **How It Works:**

- **If the user sets their OS or browser to dark mode**, the styles inside `prefers-color-scheme: dark` are applied.
    
- **If the system is in light mode**, the default or `prefers-color-scheme: light` styles apply.
    

### **Where It's Used:**

- **Operating Systems**: Windows, macOS, Android, iOS
    
- **Browsers**: Chrome, Firefox, Edge, Safari (modern versions)
    

### **Key Benefits:**

- Adapts the website to **user preferences** automatically.
    
- Improves **usability** and **accessibility** for users sensitive to bright screens.
    

### **Limitations:**

- Not supported in very old browsers.
    
- If the system is set to "automatic" (switching between light/dark based on time), changes may be unpredictable.
    

### **Conclusion:**

The `prefers-color-scheme` media query helps websites **dynamically match** the user's system theme, improving **visual comfort and accessibility**.