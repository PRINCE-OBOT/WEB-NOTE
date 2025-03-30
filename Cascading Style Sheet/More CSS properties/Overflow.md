
## Syntax 
```css

/* Keyword values */
overflow: visible;
overflow: hidden;
overflow: clip;
overflow: scroll;
overflow: auto;
overflow: hidden visible;

/* Global values */
overflow: inherit;
overflow: initial;
overflow: revert;
overflow: revert-layer;
overflow: unset;
```

The `overflow` property is specified as one or two [`<overflow>`](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow_value) keyword values. If only one keyword is specified, both `overflow-x` and `overflow-y` are set to the same value. If two keywords are specified, the first value applies to `overflow-x` in the horizontal direction and the second one applies to `overflow-y` in the vertical direction.


### [Values](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow#values)

1. [`visible`](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow#visible)

Overflow content is not clipped and may be visible outside the element's padding box. The element box is not a [scroll container](https://developer.mozilla.org/en-US/docs/Glossary/Scroll_container). This is the default value of the `overflow` property.

2. [`hidden`](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow#hidden)

Overflow content is clipped at the element's padding box. There are no scroll bars, and the clipped content is not visible (i.e., clipped content is hidden), but the content still exists.

User agents do not add scroll bars and also do not allow users to view the content outside the clipped region by actions such as dragging on a touch screen or using the scroll wheel on a mouse. The content can be scrolled programmatically (for example, by linking to anchor text, by tabbing to a hidden yet focusable element, or by setting the value of the scrollLeft property or the scrollTo() method), in which case the element box is a scroll container.


>**Using `scroll` to access information inside hidden area of the box**


```html

<!DOCTYPE html>
<html lang="en">
<head>
  <style>
   body{
     height: 100vh;
     color: red;
     display: flex;
     justify-content: center;
     align-items: center;
   }
   .con{
     width: 200px;
     height: 100px;
     border: 2px solid #000;
     padding: 3px;
     overflow: hidden visible;
   }
   .child{
     width: 500px;
     height: 100px;
     background: #672;
   }
   
  </style>
</head>
<body>
  <div class="con">
    <div class="child">Look carefully — this will be yellow. This is repeatition of a very long text yes, i mean it</div>
  </div>
  
  <script>
    const con = document.querySelector('.con')
    const child = document.querySelector('.child')
    child.addEventListener('click',()=>{
    con.scrollLeft = 500
    })
  
  </script>
</body>
</html>

```

## Other scroll properties and method [[Scroll (overflow) hidden]]...


>**Using `<a>`  or any focusable element

Any information/text that has a focusable element such as (`<a>`), with the **tab** key you can access those information that is hidden.


3. [`clip`](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow#clip)

Overflow content is clipped at the element's _overflow clip edge_ that is defined using the [`overflow-clip-margin`](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-clip-margin) property. As a result, content overflows the element's padding box by the [`<length>`](https://developer.mozilla.org/en-US/docs/Web/CSS/length) value of **overflow-clip-margin** or by `0px` if not set. Overflow content outside the clipped region is not visible, user agents do not add a scroll bar, and programmatic scrolling is also not supported. No new [formatting context](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_display/Block_formatting_context) is created. To establish a formatting context, use `overflow: clip` along with [`display: flow-root`](https://developer.mozilla.org/en-US/docs/Web/CSS/display#flow-root). The element box is not a scroll container.


4. [`scroll`](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow#scroll)

Overflow content is clipped at the element's padding box, and overflow content can be scrolled into view using scroll bars. User agents display scroll bars whether or not any content is overflowing, so in the horizontal and vertical directions if the value applies to both directions. The use of this keyword, therefore, can prevent scroll bars from appearing and disappearing as content changes. Printers may still print overflow content. The element box is a scroll container.


5. [`auto`](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow#auto)

Overflow content is clipped at the element's padding box, and overflow content can be scrolled into view using scroll bars. Unlike `scroll`, user agents display scroll bars _only if_ the content is overflowing. If content fits inside the element's padding box, it looks the same as with `visible` but still establishes a new formatting context. The element box is a scroll container.


>**Note:** The keyword value `overlay` is a legacy value alias for `auto`. With `overlay`, the scroll bars are drawn on top of the content instead of taking up space.


# Things to note

- Specifying a value other than visible (the default) or clip for overflow creates a new block formatting context. This is necessary for technical reasons; if a float intersects with a scrolling element, it would forcibly rewrap the content after each scroll step, leading to a slow scrolling experience.

```html

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>BFC Illustration</title>
  <style>
    .parent {
      border: 2px solid green;
      padding: 20px;
    }
    .float-box {
      float: left;
      width: 100px;
      height: 100px;
      background: red;
      margin-right: 10px;
    }
    .container {
      border: 2px solid blue;
      overflow: auto; /* BFC triggered */
      margin-top: 20px;
    }
    .child {
      background: lightgray;
      height: 200px;
      margin: 20px 0; /* This margin will not collapse with parent’s padding or outside elements */
    }
  </style>
</head>
<body>
  <div class="parent">
    <div class="float-box"></div>
    <div class="container">
      <div class="child">I am inside BFC — no interference from outside float!</div>
    </div>
  </div>
</body>
</html>

```



- Setting overflow to `clip` in one direction when it isn't set to `visible` or `clip` in the other direction results in the `clip` value behaving as `hidden`.

```html
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
    max-height: 300px;
    border: 2px solid #672;
    overflow-x: clip;
    overflow-y: auto;
  }
    
    p{
      margin: 0;
      inline-size: 300px;
      block-size: 400px;
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
```




- Setting overflow to `visible` in one direction (i.e. `overflow-x` or `overflow-y`) when it isn't set to `visible` or `clip` in the other direction results in the `visible` value behaving as `auto`.


```html

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
    max-height: 300px;
    border: 2px solid #672;
    overflow-x: visible;
    overflow-y: auto;
  }
    
    p{
      margin: 0;
      inline-size: 300px;
      block-size: 400px;
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
```



## [Accessibility](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow#accessibility)

A scrolling content area cannot be scrolled by a keyboard-only user, with the exception of users on Firefox (which makes the container keyboard focusable by default).


As a developer, to allow non-Firefox keyboard-only users to scroll the container, you will need to give it a [`tabindex`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/tabindex) using `tabindex="0"`. Unfortunately, when a screen reader encounters this tab-stop, they will have no context for what it is and their screen reader will likely announce the entirety of its contents. Giving it an appropriate [WAI-ARIA role](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Reference/Roles) (`role="region"`, for example) and an accessible name (via [`aria-label`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Reference/Attributes/aria-label) or [`aria-labelledby`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Reference/Attributes/aria-labelledby)) can mitigate this...

**Thereby making the screen reader to announce the Description (`aria-label`) and (`role`) instead of the entire context. 



 >**Note** `role` defines what the element is in that usage, as such using **semantics element** with `role` attributes is useless.
 
 
 
 *Example

```html

// Role defines the div element usage in this context

<div role="navigation" >
  <a>Home</a>
  <a>About</a>
</div>

// Applying role here is useless 
<nav>
  <a>Home</a>
  <a>About</a>
</nav>
```



```html
<style>
 section{
  overflow: auto;
 }
</style>

// First tabindex is added to make it scrollable with keyboard.

// Since element becomes focusable screen reader tend to read the entirety of the content.

// aria-label attributes set screen reader to read it description (Latest news) rather than the entire content.

// If user insist on reading the content, user can use Down-arrow on the keyboard.


<section aria-label="Latest news" tabindex="0">
   <p>This is a very long article...
   </p>
</section>
```


**[[WAI-ARIA]]

### **1. `role` – Defines What an Element Is**

Think of `role` as a **category label** in a library. If a sign says “Science Fiction,” you immediately know what kind of books to expect.

In HTML, `role` tells assistive technologies (like screen readers) what an element is.

**Other values is** `navigation, region...`

**Example:** A navigation menu

```html
<nav role="navigation">
  <a href="#home">Home</a>
  <a href="#about">About</a>
  <a href="#contact">Contact</a>
</nav>
```



### **2. `aria-label` – Provides a Shorter, Clearer Description**

Imagine a **museum exhibit** where an artwork has a **long, complicated name**, but there’s a small plaque with a simple description: _“Mona Lisa by Leonardo da Vinci”_.

Similarly, `aria-label` provides a **short description** when the visible text is unclear or missing.

**Example:** A button with just an icon

```html
<button aria-label="Close popup">✖</button>
```




