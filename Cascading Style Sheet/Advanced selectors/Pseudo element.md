
## **Categories of Pseudo-Elements (`::`)**

A **pseudo-element** allows you to style specific parts of an element instead of the whole element.

Pseudo-elements act as if you had added a whole new HTML element into the markup, rather than applying a class to existing elements.

**Pseudo-elements start with a double colon `::`. `::before` is an example of a pseudo-element.

---

### **Text-Related Pseudo-Elements**

These style specific parts of text content.

```css
p::first-letter {
  font-size: 2em;
  color: red;
}
```

- **What it does**: Styles only the first letter of a paragraph.
    

```css
p::first-line {
  font-weight: bold;
}
```

- **What it does**: Styles only the first line of a paragraph.
    

---

### **Content Generation Pseudo-Elements**

These allow you to add content **before** or **after** an element without modifying the HTML.

```css
p::before {
  content: "🔹 ";
  color: blue;
}
```

- **What it does**: Inserts a **blue dot** before every `<p>`.
    

```css
p::after {
  content: " 🔸";
  color: green;
}
```

- **What it does**: Inserts a **green diamond** after every `<p>`.
    

---

### **Selection Pseudo-Elements**

These apply styles when the user selects text.

```css
::selection {
  background-color: yellow;
  color: black;
}
```

- **What it does**: Changes the background and text color of selected text.
    

---

### **Form Placeholder Pseudo-Elements**

These style placeholder text inside input fields.

```css
input::placeholder {
  color: gray;
  font-style: italic;
}
```

- **What it does**: Styles the placeholder text inside an input field.



***Why you may not use `pseudo-element` in some cases 

Inserting strings of text from CSS isn't really something we do very often on the web however, as that text is inaccessible to some **screen readers** and might be hard for someone to find and edit in the future.


A more valid use of these pseudo-elements is to insert an icon, for example the little arrow added in the example below, which is a visual indicator that we wouldn't want read out by a **screen reader:

```html

<p class="box">Content in the box in my HTML page.</p>

```


```css

.box::after {
  content: " ➥";
}

```



These pseudo-elements are also frequently used to insert an empty string, which can then be styled just like any element on the page.

In this next example, we have added an empty string using the `::before` pseudo-element. We have set this to `display: block` in order that we can style it with a width and height. We then use CSS to style it just like any element. You can play around with the CSS and change how it looks and behaves.



```html

<p class="box">Content in the box in my HTML page.</p>

```

```css

box::before {
  content: "";
  display: block;
  width: 100px;
  height: 100px;
  background-color: rebeccapurple;
  border: 1px solid black;
}
```


# Chaining pseudo class and pseudo element 


```html

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Pseudo-class Example</title>
  <style>
   div {
     background: #562;
     margin: 0 0 20px 0;
   }
   p:first-child::first-letter{
     color: #f00;
   }
  </style>
</head>

<body>
  <div>
    <p>This is the first</p>
    <p>This is the first</p>
    <p>This is the first</p>
  </div>
  <div>
    <p>This is the first</p>
    <p>This is the first</p>
    <p>This is the first</p>
  </div>
  <div>
    <p>This is the first</p>
    <p>This is the first</p>
    <p>This is the first</p>
  </div>
</body>
</html>

```


