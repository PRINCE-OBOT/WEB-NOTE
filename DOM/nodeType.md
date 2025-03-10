### `nodeType` in JavaScript

`nodeType` is a property of a DOM node that returns a numeric value representing the type of the node.

#### Common `nodeType` values:

- `1` → **Element Node** (e.g., `<div>`, `<p>`, `<span>`)
- `2` → **Attribute Node** (deprecated, use `getAttribute`)
- `3` → **Text Node** (e.g., `"Hello World"` inside an element)
- `8` → **Comment Node** (e.g., `<!-- This is a comment -->`)
- `9` → **Document Node** (e.g., `document`)
- `10` → **Document Type Node** (e.g., `<!DOCTYPE html>`)
- `11` → **Document Fragment Node** (e.g., `document.createDocumentFragment()`)

#### Example Usage:

```javascript
let element = document.getElementById("myElement");
console.log(element.nodeType); // 1 (Element Node)

let textNode = element.firstChild;
console.log(textNode.nodeType); // 3 (Text Node)

let comment = document.createComment("This is a comment");
console.log(comment.nodeType); // 8 (Comment Node)
```

Would you like an example where this is useful in real-world applications?