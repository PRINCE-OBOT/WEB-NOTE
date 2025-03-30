**The cloneNode() method creates a copy of an existing element.

## Syntax:

```js

const clonedElement = element.cloneNode(deep);
```

**If deep is `true`, it copies the element and its children.

**If deep is `false`, it only copies the element itself (no children).


### Example 1: Cloning Without Children (false)

```js

const original = document.querySelector("div");
const clone = original.cloneNode(false);
document.body.appendChild(clone);
```


**This copies only the `<div>` but not its inner content.


### Example 2: Cloning With Children (true)

```js

const deepClone = original.cloneNode(true);

document.body.appendChild(deepClone);
```


**This copies the `<div>` and everything inside it.


### Key Uses of cloneNode()

1. Duplicate elements without modifying the original.

2. Efficiently create multiple copies of a template element.

3. Modify cloned elements before adding them to the DOM.