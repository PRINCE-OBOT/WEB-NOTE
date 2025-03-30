
# 1. background-clip


`background-clip` controls where the color or image is visible inside the element (content, padding, or border area).

### The values:

1. **border-box** (default):  
    The background is allowed to paint from the content area through padding and under the border.  
    
2. **padding-box**:  
    The background stops at the padding. It doesn't go under the border.  

    
3. **content-box**:  
    The background stays only in the content area — it doesn’t even enter the padding.  


4. **text** (in some browsers):  
    The background is clipped to the shape of the text itself.  
    
    

**Visual Practical Example:

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Background-clip Demo</title>
  <style>
    .box {
      width: 300px;
      height: 150px;
      margin-bottom: 30px;
      border: 10px solid black;
      padding: 20px;
      font-size: 20px;
    }
    
.border-box {
      background: radial-gradient(circle, crimson, navy);
      background-clip: border-box;
/* Make border color transparent to see the background color applied to the border */
      border:20px solid transparent;
    }
    
.padding-box {
      background: radial-gradient(circle, orange, green);
      background-clip: padding-box;
    }
    
  
.content-box {
      background: radial-gradient(circle, yellow, purple);
      background-clip: content-box;
    }


.text-box {
      background: radial-gradient(circle, yellow, purple);
    /*  background-clip: text;
Make text color transparent to be background color on it */ 
      color: transparent;
    }
    
  </style>
</head>
<body>

  <div class="box border-box">Background-clip: border-box</div>
  
  <div class="box padding-box">Background-clip: padding-box</div>
  
  <div class="box content-box">Background-clip: content-box</div>

<div class="box text">Background-clip: text</div>

</body>
</html>
```


---

# 2. Background-repeat


### 1. `repeat` (default)

**What it does:**  
The background image repeats both horizontally and vertically until the entire background is covered.  

**Practice example:**

```css
background-repeat: repeat;
```

You’ll see the image tile in both directions.


### 2. `repeat-x`

**What it does:**  
Repeats the image **only horizontally** (along the x-axis).  


**Practice example:**

```css
background-repeat: repeat-x;
```


### 3. `repeat-y`

**What it does:**  
Repeats the image **only vertically** (along the y-axis).  


**Practice example:**

```css
background-repeat: repeat-y;
```


### 4. `no-repeat`

**What it does:**  
The background image will appear **only once**.  


**Practice example:**

```css

background-repeat: no-repeat;
```


### 5. `space`

**What it does:**  
Repeats the image as many times as it can, but instead of cropping, it adds **even spacing** between repetitions so they fit perfectly.  


**Practice example:**

```css
background-repeat: space;
```

The image won’t get cropped — extra spaces are added between images.


### 6. `round`

**What it does:**  
Repeats the image and **scales** it so that a whole number of images fit into the background without cropping or leaving spaces.  

**Practice example:**

```css
background-repeat: round;
```

The browser resizes the images a bit to fit a whole number of repetitions.


---

# 3. Background-size


**1. `auto`**

- The image displays in its original size.
- If only one value is given (like `auto` or just `auto 50px`), the other dimension scales automatically to maintain the image's aspect ratio.  
    **Real-life analogy:** Imagine printing a photo and leaving it as-is, no resize.

**2. `<length> <length>` (example: `100px 50px`)**

- The first value is the width, the second is the height.
- No aspect ratio preservation.  
    **Real-life analogy:** Stretching or squishing a photo to fit a photo frame exactly, even if it distorts.

**3. `<percentage> <percentage>` (example: `50% 100%`)**

- The width and height of the image are relative to the container’s size.
- `50%` width means half the container’s width; `100%` height means as tall as the container.  
    **Real-life analogy:** Telling someone: “Print this banner at half the wall width and full wall height.”

**4. `cover`**

- The image expands as much as needed to cover the entire container.
- It may crop part of the image but will never leave empty space.  
    **Real-life analogy:** Wrapping a table with a cloth that covers the whole table, even if some parts of the cloth hang off the edges or parts of the design are not visible.

**5. `contain`**

- The image is scaled to fit inside the container completely without cropping.
- It may leave empty space (like borders).  
    **Real-life analogy:** Placing a poster inside a photo frame without cutting — the poster might show with borders around it, but you see the full image.

**6.  initial`: resets to `auto auto`.

**7. `inherit`

Takes the value from the parent element.
It forces the element to be inherited.


**8. `unset`

removes any specific value and falls back to normal behavior.

Normally `unset` should inherit from the parent if it has the property else it falls back to the default behaviour, *but* `background-size` is not inherited by default (so it always fallback to default).



---


# 4. **background-origin**

This controls where the background image starts painting from. There are three values:

- **padding-box** (default):  
    The background image starts from the padding edge.  
    **Real-life example:**  
    Imagine you have a paper with a margin, border, and padding. The image starts inside the padding area; the border is ignored.
    
- **border-box:**  
    The background image starts from the outer border edge.  
    **Real-life example:**  
    Think of a gift wrap starting from the very outer part of the box, covering even the border.
    
- **content-box:**  
    The background starts from the content edge (ignores padding and border).  
    **Real-life example:**  
    Like placing a sticker exactly inside a framed glass, without touching the padding or border.
    
**Practical test for background-origin:

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <style>
    div {
      width: 200px;
      height: 200px;
      border: 20px solid black;
      padding: 30px;
      background-image: url('https://via.placeholder.com/50');
      background-repeat: no-repeat;
      background-origin: border-box; /* Change to padding-box or content-box to see differences */
    }
  </style>
</head>
<body>
  <div></div>
</body>
</html>
```




---


# 5. **background-attachment**

This controls whether the background image scrolls with the page or stays fixed.

- **scroll** (default):  
    The background scrolls along with the content.  

    
- **fixed:**  
    The background stays fixed in the viewport; content scrolls over it.  

    
- **local:**  
    The background scrolls inside the element’s scroll area.  
    (The `local scroll` does not happens directly) - First the element must have a child with overflowing height or width - then seeing the *element* to `overflow: auto` makes it scrollable when it overflow - since the image is set to `local` it will be scrollable inside the element.
    
  *Code usage for local*
```css

<!DOCTYPE html>
<html lang="en">
<head>
  <style>
    .scroll-box {
      width: 300px;
      height: 200px;
      border: 5px solid black;
      overflow: auto;
      background: url('https://via.placeholder.com/400') no-repeat;
      background-attachment: local;
      background-size: cover;
      padding: 20px;
    }
    .content {
      height: 600px;
      font-size: 24px;
    }
  </style>
</head>
<body>
  <div class="scroll-box">
    <div class="content">
      Scroll down to see the background move with the text.
    </div>
  </div>
</body>
</html>
```



---

# 6. **`background-position`**

It controls where the background image is placed inside an element.

**value types:**

- Keywords
- Percentages
- Lengths (px, em, etc.)
- Combinations (keyword + length)

---

1. **Keyword values**

You can use one or two keywords.  
**Single keyword** values:

- `left` — aligns image to the left edge (horizontally).
- `right` — aligns to the right edge.
- `top` — aligns to the top edge (vertically).
- `bottom` — aligns to the bottom edge.
- `center` — centers the image on that axis.

**Double keywords:**

- `left top`
- `right bottom`
- `center center`  
    This is the same as saying:
- `left top` = `0% 0%`
- `center center` = `50% 50%`
- `right bottom` = `100% 100%`

 **2. Percentages**

You can use percentages to fine-tune the position.

- The first value is horizontal (0% to 100%)
- The second value is vertical (0% to 100%)

For example:

- `background-position: 20% 70%;`  
    means:
- The left edge of the image is placed at 20% across the width of the container, and 70% down the height.



 **3. Length values (px, em, rem, etc.)**

You can also use exact distances:

- `background-position: 30px 50px;`  
    This means:
- Move 30px from the left, and 50px from the top.  


**4. Mix keyword and length or percentage**

You can combine keyword and a length or keyword and percentage:

- `background-position: left 20px top 30px;`
- `background-position: right 10% bottom 5px;`  
    This gives very precise placement.

### **Default value:**

- `background-position: 0% 0%;` (top-left corner by default)
