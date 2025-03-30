

The `visibility` property in CSS controls whether an element is **visible** or **hidden** without affecting the element’s layout. Unlike `display: none`, which removes the element from the document flow, `visibility: hidden` keeps the element in place but makes it invisible.

### **All Possible Values of `visibility`**

1. **`visible` (default)**
    
    - The element is fully visible.
        
    - Example:
        
        ```css
        div {
          visibility: visible;
        }
        ```
        
2. **`hidden`**
    
    - The element is **not visible**, but it still occupies space in the layout.
        
    - Example:
        
        ```css
        div {
          visibility: hidden;
        }
        ```
        
    - Unlike `display: none`, the element remains in the document flow.
        
3. **`collapse` (for tables only)**
    
    - Works **only on table rows (`<tr>`), columns (`<col>`), and groups (`<colgroup>`)**.
        
    - Hides the row or column without affecting the table's structure.
        
    - Example:
        
        ```css
        tr {
          visibility: collapse;
        }
        ```
        
    - In some browsers, this behaves like `display: none` for table elements.
        
4. **`inherit`**
    
    - Inherits the `visibility` value from the parent element.
        
    - Example:
        
        ```css
        div {
          visibility: inherit;
        }
        ```
        
    - If the parent has `visibility: hidden`, the child will also be hidden.
        
5. **`initial`**
    
    - Resets the `visibility` to its default value (`visible`).
        
    - Example:
        
        ```css
        div {
          visibility: initial;
        }
        ```
        
6. **`unset`**
    
    - If the element has an inherited value, it behaves as `inherit`.
        
    - If not, it behaves as `initial` (which means `visible`).
        
    - Example:
        
        ```css
        div {
          visibility: unset;
        }
        ```
        
