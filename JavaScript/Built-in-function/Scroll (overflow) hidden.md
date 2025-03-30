
 *When `overflow: hidden` is used, the user can't scroll manually — but the element still behaves as a scroll container, meaning **scroll properties still work programmatically.**

Here are all the scroll-related properties that work even if the overflow is hidden:

# 1. **`scrollTop`**  

The number of pixels that the content is scrolled vertically. You can read or set it.  
    Example: `box.scrollTop = 200;`
    
# 2. **`scrollLeft`** 

The number of pixels that the content is scrolled horizontally. Also readable or writable.  

Example: `box.scrollLeft = 100;`


```css

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta http-equiv="X-UA-Compatible" content="ie=edge">
  <title>Document</title>
   <style>
  .div{
    padding: 0;
    max-width: 200px;
    border: 2px solid #672;
    overflow: hidden visible;
  }
    
    p{
      margin: 0;
      inline-size: 300px;
      background: #fce;
      font-size: 1.5rem;
    }
  </style>
</head>
<body>

<div class="div">
 <p>This controls the width of an element, but instead of using the traditional width property.</p>
 </div>
 
 <button>Button Scroll</button>


  <script>
    const div = document.querySelector('.div')
    const btn = document.querySelector('button')
    
    btn.addEventListener('click', ()=>{
     div.scrollLeft = 600
    })
  </script>
</body>
</html>


>```


>**Make sure to use selectors other than element selector when selecting the container element.


    
# 3.  **`scrollHeight`** 

The total height of the content inside the element, including the hidden parts.  
    
Example: `console.log(box.scrollHeight);`
    
# 4. **`scrollWidth`**

The total width of the content inside the element.  

Example: 

`console.log(box.scrollWidth);`
    
# 5. **`scrollBy()`**  

Allows you to scroll the content relative to its current position.  
    
Example: `box.scrollBy(0, 100);` (Scrolls down by 100px)

>**Note** when you use `element.scrollBy(0, 100)`, it scrolls **relative to the current position**.

So here’s exactly what happens:

- If you click once, the container scrolls down by 100px from its current scroll position.
    
- If you click again, it scrolls down by another 100px from wherever it stopped previously.
    
- Every click adds to the previous scroll position — it’s always moving "relative."
    
# 6. **`scrollTo()`**

Scrolls to an exact position inside the scroll container.  
    
Example: `box.scrollTo(0, 200);`

     
 **Syntax:**

There are two ways to use it:

1. **scrollTo(x, y)** — old way  
    Example:
    
```js

element.scrollTo(0, 200);  // Scroll vertically down 200px from the top`

```
    
2. **scrollTo(options)** — modern and more flexible:  
    Example:

```js

element.scrollTo({   top: 200,   left: 100,   behavior: 'smooth' // Scrolls smoothly instead of instantly(which default behaviour is 'auto' });

```
    
 **What does `scrollTo()` actually do?**

- It moves the visible part of a container or page to a new scroll position.
    
- If `overflow: hidden` is set, the content will still move inside the invisible area (like sliding a hidden drawer), but the user won’t control it — you do.


# 7. **`scrollIntoView()`** 
(called on a child element) 

If you call this on an element inside the hidden container, the parent container will automatically scroll to show it — even with `overflow: hidden`.  

**Syntax 

```js
element.scrollIntoView(options);
```

| Property | Values                                 | Meaning                                        |
| -------- | -------------------------------------- | ---------------------------------------------- |
| behavior | `auto` / `smooth`                      | How the scroll happens (instantly or smoothly) |
| block    | `start` / `center` / `end` / `nearest` | Vertical position of the element after scroll  |
| inline   | `start` / `center` / `end` / `nearest` | Horizontal positioning after scroll            |
```js

element.scrollIntoView({ inline: 'center', behavior: 'smooth' });
```


### General summary:

**Properties:** `scrollTop`, `scrollLeft`, `scrollHeight`, `scrollWidth`  

**Methods:** `scrollTo()`, `scrollBy()`, `scrollIntoView()`

