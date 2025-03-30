
The **`opacity`** [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets the opacity of an element. Opacity is the degree to which content behind an element is hidden, and is the opposite of transparency.


## [Syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/opacity#syntax)


```css

opacity: 0.9;
opacity: 90%;

/* Global values */
opacity: inherit;
opacity: initial;
opacity: revert;
opacity: revert-layer;
opacity: unset;
```


### [Values](https://developer.mozilla.org/en-US/docs/Web/CSS/opacity#values)

[`<alpha-value>`](https://developer.mozilla.org/en-US/docs/Web/CSS/opacity#alpha-value)

A [`<number>`](https://developer.mozilla.org/en-US/docs/Web/CSS/number) in the range `0.0` to `1.0`, inclusive, or a [`<percentage>`](https://developer.mozilla.org/en-US/docs/Web/CSS/percentage) in the range `0%` to `100%`, inclusive, representing the opacity of the channel (that is, the value of its alpha channel). Any value outside the interval, though valid, is clamped to the nearest limit in the range.


| Value                                                                                                  | Meaning                                                                       |
| ------------------------------------------------------------------------------------------------------ | ----------------------------------------------------------------------------- |
| `0`                                                                                                    | The element is fully transparent (that is, invisible).                        |
| Any [`<number>`](https://developer.mozilla.org/en-US/docs/Web/CSS/number) strictly between `0` and `1` | The element is translucent (that is, content behind the element can be seen). |
| `1` (default value)                                                                                    | The element is fully opaque (visually solid).                                 |


## [Description](https://developer.mozilla.org/en-US/docs/Web/CSS/opacity#description)

- `opacity` applies to the element as a whole, including its contents, even though the value is not inherited by child elements.

- If a **parent** has `opacity: 0.5;` and a **child** has `opacity: 0.2;`, the child is affected **twice**:

1. First, the child becomes **20% visible** due to its own `opacity: 0.2;`.
    
2. Then, that **20% visibility** is applied to the parent’s `50% opacity`, making it even more transparent.

So, the final visibility of the child = `0.5 * 0.2 = 0.1` (or **10% visible**).

**Example:**

```css
.parent {
  background: blue;
  opacity: 0.5;
}

.child {
  background: red;
  opacity: 0.2;
}
```

In this case, the child will be **barely visible** because it’s getting double transparency.

To change the opacity of a background only, use the [`background`](https://developer.mozilla.org/en-US/docs/Web/CSS/background) property with a [color value](https://developer.mozilla.org/en-US/docs/Web/CSS/color_value) that allows for an alpha channel. For example:


```css

background: rgb(0 0 0 / 40%);
```

When `opacity` value is set to `0`, the element and all of its children appear invisible, but they are still part of the DOM. That means they still register [pointer events](https://developer.mozilla.org/en-US/docs/Web/API/Pointer_events) and, if the elements are in a tabbing order, they do get focus. For good usability, make sure to make such elements visible when they receive user interactions or use the CSS [`pointer-events`](https://developer.mozilla.org/en-US/docs/Web/CSS/pointer-events) property to disable pointer events and take the element out of the tab order by disabling with the `disabled` attribute or setting [`tab-index="-1"`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/tabindex) for non-form-related interactive elements.

*Setting `tabindex="-1"` means the element **is not focusable via the Tab key**, but it **can still be focused programmatically** (e.g., using JavaScript).

```css
div{
 opacity : 0;
}
```

```html


  <div tabindex="-1">Box</div>
  
```

```js

<script>
    const div = document.querySelector('div')
    
    div.addEventListener('focus', ()=>{
      alert('Focused')
    })
</script>
```


Using `opacity` with a value other than `1` places the element in a new [stacking context](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_positioned_layout/Stacking_context).

```html


<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta http-equiv="X-UA-Compatible" content="ie=edge">
  <title>Document</title>
  <style>
    div{
      width: 200px;
      height: 200px;
      margin: 0 0 20px 0;
      border: 2px solid #355;
    }
    section{
      background: lightblue;
    }
  
   div:first-child{
      background: #672;
      position: absolute;
      top: 10px;
      left: 10px;
      right: 200px;
      bottom: 200px;
    }
   div:last-child{
      background: #637;
      opacity: 0.5;
    }
  
  </style>
</head>
<body>
  <section>
  <div>Box</div>
  <!-- Last element stays on top -->
  <!-- Box 1 create a new stacking context been on top-->
  <!-- Box 2 retake his place in the context by setting opacity value less than 1 -->
  <div>Box</div>
  </section>
  
  <script>
    const box1 = document.querySelector('div:first-child')
    const box2 = document.querySelector('div:last-child')
    
    box1.addEventListener('click', ()=>{
      alert('Box1')
    })
  
    box2.addEventListener('click', ()=>{
      alert('Box2')
    })
  </script>
</body>
</html>
```



Color contrast ratio is determined by comparing the luminosity of the opacity-adjusted text and background color values. In order to meet current [Web Content Accessibility Guidelines (WCAG)](https://www.w3.org/WAI/standards-guidelines/wcag/), a ratio of 4.5:1 is required for text content and 3:1 for larger text such as headings. Large text is defined as 18.66px and [bold](https://developer.mozilla.org/en-US/docs/Web/CSS/font-weight) or larger, or 24px or larger.

***How to calculate the ratio of the contrast text ratio.

 - Provide the text background color  (background)
 
 - Provide the text color (foreground)
 
 - Provide the opacity values if included (Alpha).  
 
  >**Upload these information here: [[https://webaim.org/resources/contrastchecker/]]
