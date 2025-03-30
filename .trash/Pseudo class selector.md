

**Pseudo class selectors** target some bit of your document that is in a certain state, behaving as if you had added a class into your HTML. Take a look at some other examples on MDN:


>**Note:** It is valid to write pseudo-classes and elements without any element selector preceding them. In the example above, you could write `:first-child` and the rule would apply to _any_ element that is the first child of an `<article>` element, not just a paragraph first child — `:first-child` is equivalent to `*:first-child`. However, usually you want more control than that, so you need to be more specific.