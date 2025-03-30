The `text-shadow` CSS property applies one or more shadows to text and its decorations. Each shadow consists of:

1. **Offset-X & Offset-Y (required)** – Defines the horizontal and vertical position of the shadow. Negative values move the shadow left (X) or up (Y).
2. **Blur Radius (optional)** – Controls the softness of the shadow. Defaults to `0` (sharp shadow).
3. **Color (optional)** – Defines the shadow’s color. If omitted, the browser may apply a default color.

Multiple shadows are applied in order, with the first appearing on top. The default value is `none`.

### Shorthand Syntax:

```css
text-shadow: <offset-x> <offset-y> <blur-radius>? <color>?;
```

### Examples:

```css
/* Single shadow */
text-shadow: 3px 3px 5px gray;

/* Multiple shadows */
text-shadow: 
  2px 2px 4px black, 
  -2px -2px 4px red, 
  1px 1px 2px blue;

/* No blur */
text-shadow: 2px 2px black;

/* Only offsets, default blur and color */
text-shadow: 4px 4px;
```

### Example with Multiline Text:

```css
p {
  text-shadow: 1px 1px 2px black, 0 0 1em blue, 0 0 0.2em blue;
  color: white;
  font-size: 1.5em;
  text-align: center;
}
```

