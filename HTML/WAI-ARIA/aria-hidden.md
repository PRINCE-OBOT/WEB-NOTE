### **`aria-hidden` Attribute Explained**

The `aria-hidden` attribute is used to **control whether an element is exposed to assistive technologies**, such as screen readers. It has two possible values:

#### **1. `aria-hidden="true"`**

- The element **remains visible** on the screen but **is ignored** by screen readers.
    
- Use it for **decorative elements**, redundant text, or things that shouldn't be read aloud (e.g., duplicate navigation links).
    
- Example:
    
    ```html
    <p aria-hidden="true">This text is visible but ignored by screen readers.</p>
    ```
    

#### **2. `aria-hidden="false"`**

- The element **is exposed** to screen readers.
    
- This is **not needed** in most cases because screen readers already read visible elements by default.
    
- It’s only useful when `aria-hidden="true"` is set on a parent and you want to **override** it for a child element.
    
- Example:
    
    ```html
    <div aria-hidden="true">
      <p aria-hidden="false">This paragraph will still be read by screen readers.</p>
    </div>
    ```
    

#### **3. `aria-hidden` Removed (No Attribute)**

- If `aria-hidden` is **not present**, screen readers will **automatically** read the element if it is visible.
    
- This is the default behavior.
    

---

### **Key Considerations**

- **Does `aria-hidden="true"` make an element invisible?**  
    No, it is still **visible on the screen**, but assistive technologies ignore it.
    
- **Does `aria-hidden="true"` remove keyboard focus?**  
    No, interactive elements (buttons, links) **can still be focused** unless `tabindex="-1"` is set.
    
- **Should I use `aria-hidden="true"` for important content?**  
    No, avoid hiding meaningful content from screen readers unless absolutely necessary.
    

