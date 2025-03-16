

### 1. **How Antialiasing Works in CSS**

In CSS, you can control text antialiasing using the `-webkit-font-smoothing` and `text-rendering` properties


**This property affects how fonts are rendered on macOS and iOS, it has not effect in windows, Linux as it is (antialiased) by default.

- `-webkit-font-smoothing: antialiased;` → Makes text thinner and smoother by reducing contrast.

- `-webkit-font-smoothing: subpixel-antialiased;` → Default setting, retains contrast and sharpness.

- `-webkit-font-smoothing: none;` → Disables smoothing, making text appear jagged.

Example:

```css
body {
  -webkit-font-smoothing: antialiased;
}
```

#### **2. `text-rendering` (For Better Font Display Across Browsers)**

This property helps optimize how text is displayed based on readability, speed, or precision.

- `text-rendering: optimizeLegibility;` → Enhances readability by enabling ligatures and kerning.
- `text-rendering: optimizeSpeed;` → Prioritizes faster text rendering over quality.
- `text-rendering: geometricPrecision;` → Makes text sharper, often used for precise UI elements.

Example:

```css
h1 {
  text-rendering: optimizeLegibility;
}
```

