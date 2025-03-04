As the name imply it is just a parent container of a child.

```
STYLE 

 ​.replaceStyle{
        color: red;
        background:lightpink;
        font-weight:700;
      }

HTML

`<div class="father">Father       <div class="child">
        child</div>
</div>
```

From the description, `child
has a **parentNode** of `father`

```JavaScript
const child = document.querySelector(".child")

child.parentNode.classList.toggle("replaceStyle")`
```


What the code does is replace the `class` of the child parent and apply the class `replaceStyle` to it.

*Interesting thing is: if there is any styles made already in case with that class name, it then take the style.*
