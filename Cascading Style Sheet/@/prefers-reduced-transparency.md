

The `prefers-reduced-transparency` media query is used to detect whether the user has enabled settings to **reduce transparency and animations** on their device. This is particularly useful for users who may have difficulty with visual content that includes transparent elements or excessive visual effects (such as blurs or transparencies), which can be overwhelming or hard to see.

### **Key Points:**

- **Purpose**: It targets users who have set a preference to reduce transparency, often for accessibility reasons (e.g., users with low vision or sensitivity to motion).
    
- **Common Use**: It’s used to adjust UI elements that might have transparent backgrounds or blur effects, such as glassmorphism designs or modal windows with transparency.
    
- **How It Works**:
    
    - If the user has **enabled** transparency reduction on their device, the styles inside the media query will be applied.
        
    - If the user has **disabled** the transparency reduction, the default styles are applied.


## How to enable setting for `prefers-reduced-transparency` on Android 

- Go to setting
- Click accessibility 
- Activate **High Contrast Mode**

### **Syntax**:

```css
@media (prefers-reduced-transparency: reduce) {
  /* Styles to reduce transparency or visual effects */
}
```

- `reduce`: Tells the browser to apply the styles that reduce transparency effects.
    

### **Example**:

```css
@media (prefers-reduced-transparency: reduce) {
  .background {
    background: rgb(255, 255, 255); /* Use solid white instead of transparent background */
  }
  .modal {
    backdrop-filter: none; /* Disable blur effects */
  }
}
```

### **Where It’s Supported**:

- **Browsers**: Some browsers (mainly newer versions of Chrome, Firefox, and Safari) support `prefers-reduced-transparency`.
    
- **Operating Systems**: It's supported on platforms like iOS, macOS, and Windows for accessibility settings.
    

### **Limitations**:

- Not all browsers or devices may expose this preference to websites.
    
- In some cases, **High Contrast Mode** may override transparency settings, making it difficult to detect the **Reduce Transparency** setting.
    

### **Conclusion**:

The `prefers-reduced-transparency` media query is a useful tool to make websites more accessible by respecting user preferences for transparency reduction, helping those with visual impairments or sensitivity to visual effects. However, it’s not universally supported across all devices and browsers.