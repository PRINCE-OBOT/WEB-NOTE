**You can modify an element’s attributes dynamically using the `.setAttribute(), .getAttribute(), and .removeAttribute() methods.`


```
const element = document.querySelector("div");

// Set class attribute
element.setAttribute("class", "active");

// Get class attribute
console.log(element.getAttribute("class"));

// Remove class attribute
element.removeAttribute("class");
```