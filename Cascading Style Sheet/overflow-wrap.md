The `overflow-wrap` property has the following values:

### **1. `normal` (Default)**

- Words **do not break** unless necessary.
- If a word is too long and cannot fit within its container, it may **cause overflow**.

```css
p {
  overflow-wrap: normal;
}
```

### **2. `break-word` (Legacy)**

- Forces long words to **break and wrap** onto the next line **if they exceed the container width**.
- This is similar to `word-break: break-word;` but follows more modern rules.

```css
p {
  overflow-wrap: break-word;
  hyphens: auto; /* Add hyphen when word break */
}
```

### **3. `anywhere` (Newer)**

- Similar to `break-word`, but **more aggressive**.
- Allows words to break **even if it's not necessary**, preventing overflow.

```css
p {
  overflow-wrap: anywhere;
}
```

- **Example use case:** If you want to avoid horizontal scrolling at all costs, use `anywhere`.

### **Key Differences Between `break-word` and `anywhere`:**

- `break-word` **only breaks when necessary** (e.g., at the container’s edge).
- `anywhere` **allows breaks even when not necessary**, making text more flexible.

Would you like a practical test to see the differences in action?