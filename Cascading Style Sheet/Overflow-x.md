### **`overflow-x`**

`overflow-x` controls how content behaves when it overflows horizontally. It has four main values:

1. **`visible` (default)** – Content spills outside without being clipped.
2. **`hidden`** – Overflowing content is clipped and not scrollable.
3. **`scroll`** – Always shows a horizontal scrollbar, even if there’s no overflow.
4. **`auto`** – Shows a scrollbar **only** when the content overflows.

---

### **Example Code:**

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Overflow-X Example</title>
  <style>
    .container {
      width: 300px;
      height: 100px;
      border: 2px solid black;
      overflow-x: auto; /* Enables horizontal scrolling when needed */
      white-space: nowrap; /* Prevents text from wrapping */
    }

    .content {
      width: 600px; /* Exceeds container width, forcing overflow */
      background: lightblue;
    }
  </style>
</head>
<body>

  <div class="container">
    <div class="content">
      This is a long text inside a small box. Scroll horizontally to see the full content.
    </div>
  </div>

</body>
</html>
```

### **Explanation:**

- The `.container` has a fixed width (`300px`), but the `.content` inside is wider (`600px`).
- `overflow-x: auto;` ensures a horizontal scrollbar appears **only** if needed.
- `white-space: nowrap;` prevents the text from wrapping to a new line.

