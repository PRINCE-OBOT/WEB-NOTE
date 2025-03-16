
### What is `:focus-within`?

The `:focus-within` CSS pseudo-class applies styles to an element when **any of its descendants** (children, grandchildren, etc.) receive focus.

### Why use `:focus-within`?

Normally, `:focus` only applies to elements that can receive focus (like `<input>` or `<button>`). But `:focus-within` allows you to style a **parent** element when any of its children are focused.

### Example:

```html
<label class="input-container">
  Username:
  <input type="text">
</label>
```

```css
.input-container {
  display: flex;
  padding: 5px;
  background-color: lightgray;
  transition: background-color 0.3s;
}

.input-container:focus-within {
  background-color: lightblue; /* Changes when input is focused */
}
```

### How it works:

1. The `label` has a default gray background.
2. When the user clicks on the `<input>`, the parent `label` gets a blue background.
3. The effect stays as long as the `<input>` is focused.
