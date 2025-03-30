
Line length is the number of characters on a single line of text before it wraps. There’s no direct CSS property called `line-length`, but you can control it by setting the container’s width using units like `ch`, `em`, `rem`, `px`, or `%`.

A good, readable line length is around 50–75 characters.  
Example:

```css
p {
  max-width: 60ch;
}
```

This ensures each line holds about 60 characters for better readability.

