The `<picture>` element in HTML is used for **responsive images**, allowing different image sources based on screen size, resolution, or format support.

### **How It Works**

- It contains multiple `<source>` elements, each specifying a different image.
- The browser **chooses the best matching image** based on screen size or format support.
- The `<img>` inside `<picture>` serves as a **fallback** if no `<source>` matches.

### **Basic Example**

```html
<picture>
  <source srcset="image.webp" type="image/webp">
  <source srcset="image-large.jpg" media="(min-width: 600px)">
  <img src="image.jpg" alt="A sample image">
</picture>
```

- If the browser supports **WebP**, it loads `image.webp`.
- If the screen is **600px or wider**, it loads `image-large.jpg`.
- If none of the conditions match, it loads **`image.jpg`** (fallback).

### **Key Takeaways**

- `<picture>` does not render images directly, **only `<img>` does**.
- `<source>` elements **provide choices**, but the browser picks one.
- Always include an `<img>` for **fallback support**.
