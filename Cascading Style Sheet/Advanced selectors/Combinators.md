

### **What is a Pseudo-Element?**

A **pseudo-element** is a special CSS selector that allows you to style **specific parts of an element** without needing extra HTML markup.

***class** or **id** in HTML is considered markup because they are attributes used to structure and identify elements within an HTML document.*

# Combinators 

`*`          all elements
div        all div tags
div,p     all divs and paragraphs
div p    paragraphs inside divs
div > p      all p tags, one level deep                      in div

div + p    p tags immediately after div
div ~ p    p tags preceded by div
.classname      all elements with class

#idnameelement   with ID
div.classname        divs with certain                                    classname
div#idnamediv       with certain ID

#idname *all elements inside #idname


```css

p {
  ~ img {
  }
}
/* This is parsed by the browser as */
p ~ img {
}
```


The [`&` nesting selector](https://developer.mozilla.org/en-US/docs/Web/CSS/Nesting_selector) can also 
```css

p {
  & img {
  }
}
/* This is parsed by the browser as */
p img {
}
```


```css

body {
  font-family: sans-serif;
}

h1 {
  & ~ p {
    /* this is parsed by the browser as h1 ~ p */
    font-weight: bold;
    background-color: #333;
    color: #fff;
    padding: 0.5em;
  }
  ```

***Combinators are important because in [[Content Management System]] environment we may not have direct control to provide custom class, with just our CSS combinators we can style our HTML elements.