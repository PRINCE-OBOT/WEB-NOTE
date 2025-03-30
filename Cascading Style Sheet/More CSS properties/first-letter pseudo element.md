
### How background-size  value behave in `first-letter`


```css
background-position: left 10% top 10%;
```

means:

- Start from the **left edge**, move inward by **10%** horizontally.
- Start from the **top edge**, move inward by **10%** vertically.

**But in `::first-letter` pseudo-elements, yes — the interpretation changes.**

The spec says:

> "For `::first-letter` pseudo-elements, percentage values are relative to the `::first-letter` box, but positioning keywords like `top` and `left` are swapped in direction."

**What this means practically:**

- `left` acts like `right`
- `top` acts like `bottom`
- `right` acts like `left`
- `bottom` acts like `top`

So, in `::first-letter`:

```css
background-position: left 10% top 10%;
```

actually behaves like:

- `left` is treated as `right` — so it positions from the right edge.
- `top` is treated as `bottom` — so it positions from the bottom edge.

 