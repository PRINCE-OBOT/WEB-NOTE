### **What is `padding-inline` in CSS?**

`padding-inline` is a **logical property** in CSS that sets the **left and right padding** of an element **based on writing direction**. Unlike `padding-left` and `padding-right`, which are **physical properties**, `padding-inline` automatically adjusts to different text directions like **left-to-right (LTR)** and **right-to-left (RTL)**.

---

### **Syntax**

```css
padding-inline: <start> <end>;
```

- If **one value** is given, it applies **equal padding** on both the start and end sides.
- If **two values** are given, the **first** applies to the **start side** and the **second** applies to the **end side**.

---

### **Example 1: Single Value (Same on Both Sides)**

```css
.box {
  padding-inline: 20px;
  background: lightblue;
}
```

This applies **20px padding on both inline sides** (left and right in LTR, right and left in RTL).

---

### **Example 2: Different Values for Start and End**

```css
.box {
  padding-inline: 10px 30px;
  background: lightgreen;
}
```

- In **LTR**: `10px` applies to the **left**, `30px` applies to the **right**.
- In **RTL**: `10px` applies to the **right**, `30px` applies to the **left**.

---

```css

p{
   padding-inline: 10px 60px;
 }
 p:first-child{
   direction: ltr;
 }
 p:last-child{
   direction: rtl;
 }
```


```html

<div>
 <p>
   This is the begining of the whole situation where every whole situation where every whole situation where every whole situation where every
 </p>
 <p>
   هذه هي بداية الوضع بأكمله حيث كل وضع بأكمله حيث كل وضع بأكمله حيث كل وضع بأكمله حيث كل
 </p>
 </div>
```

### **Why Use `padding-inline`?**

1. **Better for Multi-Language Support** → Adapts automatically for LTR and RTL languages.
2. **More Readable & Maintainable** → Instead of writing separate `padding-left` and `padding-right`, one rule covers both.
3. **Future-Proof** → Works well with **flexbox** and **grid layouts**.
