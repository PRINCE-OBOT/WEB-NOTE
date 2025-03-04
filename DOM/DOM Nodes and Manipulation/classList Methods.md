Using classList Methods to Work with Classes

**Instead of modifying styles directly, you can toggle, add, or remove classes dynamically:

```
const box = document.querySelector(".box");

// Add a class
box.classList.add("active");

// Remove only the class name
box.classList.remove("active");

// Add class if element does not have the class, else remove it.
box.classList.toggle("hidden");
```

---

This method of using CSS classes instead of inline styles helps keep your code cleaner and more maintainable. Let me know if you want any modifications!
