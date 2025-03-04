**Appending Elements Using JavaScript

You can add elements dynamically using different methods like **append(), appendChild().

**Note** **appendChild()** can only append a single node at a time. If you try to pass multiple nodes, it will throw an error, and it does not append string.

However, **append()** can append multiple nodes or text at once and accept string.

## appendChild() 

```
const parent = document.querySelector("div");
const newElement = document.createElement("p");

newElement.textContent = "This is a new paragraph.";

parent.appendChild(newElement);
```

## append() 

*Appending single node*

```
const newPara = document.createElement("p");

newPara.textContent = "Another paragraph.";

parent.append(newPara);
```

*Appending multiple node*

```
const newPara = document.createElement("p");

newPara.textContent = "Another paragraph.";

parent.append(newPara, " Some extra text");
```

