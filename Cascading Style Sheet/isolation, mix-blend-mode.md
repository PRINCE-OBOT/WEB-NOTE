## How isolate behave

### 1.

When a parent has `mix-blend-mode` property, it affects not just itself but also its children by default. The children will blend **relatively to the parent's background**, unless they have their own `mix-blend-mode`, which then blends them with the parent instead.
```html

<div class="container">
    container
    <div class="child">
      child
      <div class="little">
        little
      </div>
    </div>
  </div>
```

```css

body{
  background: grey;
}

.parent {
  background: green;
  mix-blend-mode: difference;
}

.child {
  background: red;
  width: 100px;
  height: 100px;
/*Child get blend too, unless explicitly set with mix-blend-mode then it blend to the parent background*/
}
```
### 2. 

When the parent has transparency or no background, `isolation: isolate` will prevent the children from blending with the parent own parent else it becomes less noticeable.
 
  **Example 1

```css

body{
  background: grey;
}

.parent {
  isolation: isolate;
  background: green;
/*Because of the background color no visible isolation*/
}

.child {
  mix-blend-mode: difference;
  background: red;
  width: 100px;
  height: 100px;
}
```

**Example 2

```css

body{
  background: grey;
}

.parent {
  isolation: isolate;
  /*Visible isolation behaviour*/
}

.child {
  mix-blend-mode: difference;
  background: red;
  width: 100px;
  height: 100px;
}
```


# Values of mix-blend-mode

The `mix-blend-mode` property in CSS controls how an element’s content blends with the content behind it. Here are all the possible values:

### **1. Normal Mode**

- `normal` → No blending; the element is displayed as usual.

### **2. Darkening Modes** (Make the result darker)

- `multiply` → Multiplies colors, making overlapping areas darker.
- `darken` → Keeps the darkest color between the element and the background.
- `color-burn` → Darkens the background by increasing contrast.

### **3. Lightening Modes** (Make the result lighter)

- `screen` → Inverts, multiplies, and inverts again, making the result brighter.
- `lighten` → Keeps the lightest color between the element and the background.
- `color-dodge` → Brightens the background by reducing contrast.

### **4. Contrast Modes** (Increase contrast between elements)

- `overlay` → Mix of `multiply` and `screen`, increasing contrast.
- `hard-light` → Similar to `overlay` but based on the element instead of the background.
- `soft-light` → Similar to `hard-light` but produces a softer effect.

### **5. Inversion & Difference Modes**

- `difference` → Subtracts pixel values, creating an inverted effect.
- `exclusion` → Similar to `difference` but with lower contrast.

### **6. Component-Based Modes**

- `hue` → Uses the hue of the element while keeping the background's saturation and luminosity.
- `saturation` → Uses the element's saturation while keeping the background's hue and luminosity.
- `color` → Uses the element's hue and saturation while keeping the background's luminosity.
- `luminosity` → Uses the element's luminosity while keeping the background's hue and saturation.
