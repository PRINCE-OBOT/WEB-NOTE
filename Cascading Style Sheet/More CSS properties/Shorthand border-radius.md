

The `border-radius` shorthand allows setting all four corners in one go:

- You can use **one**, **two**, **three**, or **four** values.
- Optionally, you can separate horizontal and vertical radii with a slash (`/`).

**Basic syntax:**

```css
border-radius: <top-left> <top-right> <bottom-right> <bottom-left>;
```

**Number of values:**

- **1 value:** applies to all corners.
- **2 values:** first value for top-left & bottom-right, second value for top-right & bottom-left.
- **3 values:**
    - first for top-left
    - second for top-right & bottom-left
    - third for bottom-right
- **4 values:** follow clockwise order: top-left, top-right, bottom-right, bottom-left.

**Example:**

```css
border-radius: 10px;                /* all corners 10px */
border-radius: 10px 20px;           /* TL & BR = 10px; TR & BL = 20px */
border-radius: 10px 20px 30px 40px; /* TL=10px, TR=20px, BR=30px, BL=40px */
```

**Advanced (elliptical corners):**

```css
border-radius: 50px / 20px;  
```

- `50px` is horizontal radius for all corners,
- `20px` is vertical radius for all corners.
