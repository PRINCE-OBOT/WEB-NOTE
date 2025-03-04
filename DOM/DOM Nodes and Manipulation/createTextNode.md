It's basically for interactive appending of text to HTML elements. 

```
HTML
<p> Hi </p>

SCRIPT

const p = document.querySelector("p")
const addText = document.createTextNode('Prince')
 
p.appendChild(addText)
```

## Why not use  p += 'prince' to append text

**Note** The trick fact about **createTextNode** is it does not actually alter the existing elements, is separate raw node text is being appended to the existing element, but any style given to the actual element is being inherited by the createTextNode.