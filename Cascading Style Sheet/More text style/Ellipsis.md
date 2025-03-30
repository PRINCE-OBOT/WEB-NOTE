The `text-overflow: ellipsis;` property is used to indicate that text has been cut off when it overflows its container. It works only on **single-line text** and requires `white-space: nowrap;` and `overflow: hidden;` to function properly.

### Example:

```css
.ellipsis-text {
  width: 200px; /* Set a fixed width */
  white-space: nowrap; /* Prevent text from wrapping */
  overflow: hidden; /* Hide the overflowing text */
  text-overflow: ellipsis; /* Show "..." when text overflows */
  border: 1px solid black; /* Just for visibility */
}
```

```html
<p class="ellipsis-text">This is a very long text that should be truncated with an ellipsis.</p>
```

### Explanation:

1. **`white-space: nowrap;`** prevents text from wrapping to the next line.
2. **`overflow: hidden;`** ensures that any overflowing text is not displayed.
3. **`text-overflow: ellipsis;`** replaces the cut-off text with "...".
