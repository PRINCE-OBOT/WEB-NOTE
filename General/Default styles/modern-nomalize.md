
The [modern-normalize](https://github.com/sindresorhus/modern-normalize) library does the traditional job of a normalize stylesheet, plus adds some opinionated defaults of its own. It’s available as an npm package, or you can [grab the CSS](https://github.com/sindresorhus/modern-normalize/blob/main/modern-normalize.css) directly.

Here’s what I appreciate about modern-normalize:

- It removes styles that was supported by old browsers.

- It disables the weird `-webkit-text-size-adjust` behavior on iOS that causes text to zoom when the device is rotated from portrait to landscape.

- It sets `system-ui` as the default font (with fallbacks) for a clean, modern look; much nicer than Times New Roman.

- It ensures that form inputs and buttons match the document’s font and text size (`font-family: inherit` and `font-size: 100%`).

- It removes the default margin on the `<body>` element.
- It globally applies `box-sizing: border-box`. Yay!


```css

@import "modern-normalize";

:root {
  line-height: 1.5;
}

h1, h2, h3, h4, h5, figure, p, ol, ul {
  margin: 0;
}

ol[role="list"], ul[role="list"] {
  list-style: none;
  padding-inline: 0;
}

h1, h2, h3, h4, h5 {
  font-size: inherit;
  font-weight: inherit;
}

img {
  display: block;
  max-inline-size: 100%;
}
```