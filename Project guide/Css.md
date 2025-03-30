# Declare font-face
 
 >Means having tools in place before the external CSS loads and use it.

Declaring @font-face and a few style make in inline style, reduce the work for external CSS, to avoid blocking of text rendering.

```css

<head>
  <style>
    @font-face {
      font-family: "Open Sans";
      src: url("/fonts/OpenSans-Regular-webfont.woff2") format("woff2");
    }
    body {
      font-family: "Open Sans";
    }
  </style>
  <link rel="stylesheet" href="styles.css">
</head>
```


// Use `ch` for text content 

```css

article {
  max-inline-size: 66ch;
}
```


// Use `1.5` for line-height 

```css

article{
line-height: 1.5;
}
```