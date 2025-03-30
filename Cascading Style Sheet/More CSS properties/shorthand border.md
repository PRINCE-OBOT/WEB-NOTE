

The `border` shorthand combines:

- **border-width**
- **border-style** (this is required)
- **border-color**

**Syntax:**

```css
border: <border-width> <border-style> <border-color>;
```

All parts are optional except **border-style**, but if you skip width or color, they’ll use default values.

**Examples:**

```css
border: 2px solid red; /* width, style, color */
border: solid blue;    /* style, color — width defaults to medium */
border: dashed;        /* style only — width=medium, color=element color */
```

**What each part means:**

- **Width:** can be `thin`, `medium`, `thick`, or any length (e.g., `4px`, `0.2em`).
- **Style:** must be one of: `solid`, `dashed`, `dotted`, `double`, `groove`, `ridge`, `inset`, `outset`, `none`, or `hidden`.
- **Color:** any color value.




