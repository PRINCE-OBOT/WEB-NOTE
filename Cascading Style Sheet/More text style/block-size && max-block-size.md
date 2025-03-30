


#### **What is `block-size`?**

`block-size` defines the height of an element, but instead of using the traditional `height` property (which works in a top-to-bottom direction), `block-size` follows the **block flow direction** based on the writing mode of the document.

- In **English (left-to-right, top-to-bottom)**: `block-size` behaves like `height`.
    
- In **Japanese (top-to-bottom, right-to-left)**: `block-size` behaves like `width`.
    

##### **Example of `block-size` (English writing mode)**

```css
div {
  writing-mode: horizontal-tb; /* Default in English */
  block-size: 200px;
  background: lightblue;
}
```

This sets the height to `200px`, just like `height: 200px` would.

##### **Example of `block-size` (Japanese writing mode)**

```css
div {
  writing-mode: vertical-rl; /* Text flows vertically */
  block-size: 200px;
  background: lightblue;
}
```

Here, `block-size` acts more like `width`, because the content flows vertically.

---

#### **What is `max-block-size`?**

`max-block-size` sets the **maximum height** an element can grow in the block direction. If the content is smaller, the element can shrink, but if it’s larger, it will be constrained to this max value.

##### **Example of `max-block-size`**

```css
div {
  max-block-size: 150px;
  overflow: auto;
  background: lightcoral;
}
```

If the content inside the `<div>` is taller than `150px`, it will create overflow.

---

#### **How Do They Affect Overflow?**

- If `block-size` is set and content exceeds it, overflow occurs.
    
- If `max-block-size` is set, the element will grow **only up to that size** before triggering overflow.
    
- Without these properties, elements expand freely to fit their content, preventing overflow from happening.
    
