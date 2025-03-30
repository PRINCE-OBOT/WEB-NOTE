

**When you need an element inside a constrained container to stretch across the full viewport width, you can use:

>**Note** when the dimensions of the margin is % (percentage) it is relative to the parent **width**, while **px** is relative to the **height**.

```css
.full-width {
  margin-left: calc(50% - 50vw);
  margin-right: calc(50% - 50vw);
}
```

Here’s how it works:

- **`50%`** refers to half of the element's width (relative to its container).
- **`50vw`** refers to half of the viewport width.
- The `calc(50% - 50vw)` formula shifts the element outward, ensuring it fills the entire screen.

This is useful when working with CMS or static-site generators that restrict markup control.