


### **`inline-size`**

#### **What is `inline-size`?**

`inline-size` controls the width of an element, but instead of using the traditional `width` property, it follows the **inline flow direction**, which depends on the document’s writing mode.

- In **English (`writing-mode: horizontal-tb`)**, `inline-size` behaves like `width`.
    
- In **Japanese (`writing-mode: vertical-rl`)**, `inline-size` behaves like `height`.
    

#### **Example of `inline-size` (English writing mode)**

```css
div {
  writing-mode: horizontal-tb; /* Default in English */
  inline-size: 300px;
  background: lightblue;
}
```

This sets the width to `300px`, just like `width: 300px`.

#### **Example of `inline-size` (Japanese writing mode)**

```css
div {
  writing-mode: vertical-rl; /* Text flows vertically */
  inline-size: 300px;
  background: lightblue;
}
```

Here, `inline-size` acts like `height` because text flows from top to bottom.



### **What is `max-inline-size` in CSS?**

`max-inline-size` is a **logical property** in CSS that sets the **maximum width** of an element **based on the text direction** (LTR or RTL). It works like `max-width` but respects the **writing mode** of the content.

---

### **How It Works**

- In **left-to-right (LTR) languages** like English, `max-inline-size` controls the **maximum width** (like `max-width`).
- In **right-to-left (RTL) languages** like Arabic, it still applies to the **horizontal direction** but respects the writing flow.
- In **vertical writing modes** (e.g., Chinese `writing-mode: vertical-rl`), `max-inline-size` controls **height instead of width**.

---

### **Syntax**

```css
max-inline-size: <value>;
```

- `<value>` can be `px`, `em`, `%`, `auto`, etc.
- If the content is **smaller** than the max size, it stays the same.
- If the content **exceeds** the max size, it shrinks to fit.

---

### **Example 1: Limiting Width (LTR & RTL)**

```css
.box {
  max-inline-size: 300px;
  background: lightblue;
}
```

- In **LTR (English)**, this behaves like `max-width: 300px;`.
- In **RTL (Arabic, Hebrew)**, it still limits width but respects RTL flow.

---

### **Example 2: Works in Vertical Writing Modes**

```css
.box {
  writing-mode: vertical-rl; /* Text flows top to bottom */
  max-inline-size: 200px;
  background: lightgreen;
}
```

- Here, `max-inline-size` limits **height**, not width, because the text flows vertically.

---

### **Why Use `max-inline-size` Instead of `max-width`?**

1. **Better for Multi-Language Support** – Works in both LTR and RTL layouts.
2. **Adapts to Vertical Text** – Useful for East Asian languages like Chinese, Japanese, and Korean when using vertical writing modes.
3. **Future-Proof and Readable** – Keeps styles clean and flexible for different layouts.

