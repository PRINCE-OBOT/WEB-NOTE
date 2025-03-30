

## 1. **Font Type (`@font-face`)**

    
- Custom fonts are loaded using `@font-face`.
    
	- Each `@font-face` rule defines a `font-family name src, font-weight, font-style, size-adjust, unicode-range and stretch`.
    
	- The browser selects the best-matching font when rendering text.


## 2. **Font-Weight** Defaults(normal(400) )
    
- Numeric values range from **100 (thin) to 900 (black)**.
    
	- If no exact match exists, the browser picks the closest weight.


## 3. **Font-Style** Defaults (normal)
    
- Can be **normal, italic, or oblique**.
    
	- If no `italic` font is available, the browser may artificially slant the normal font.
    

```css
@font-face {
  font-family: myFont;
  src: url(Regular.ttf);
  font-weight: 400;
  font-style: normal;
}

@font-face {
  font-family: myFont;
  src: url(Bold.ttf);
  font-weight: 700;
  font-style: normal;
}

@font-face {
  font-family: myFont;
  src: url(Italic.ttf);
  font-weight: 400;
  font-style: italic;
}

body {
  font-family: myFont;
  font-weight: 500; /* No exact match → Falls back to 400 */
  font-style: normal; /* Finds Regular.ttf */
}

h1 {
  font-family: myFont;
  font-weight: 700; /* Exact match → Uses Bold.ttf */
}

p {
  font-family: myFont;
  font-style: italic; /* Exact match → Uses Italic.ttf */
}
```

### **What Happens in Practice**

- `body` requests **`font-weight: 500`**, but since **500 isn’t available**, it falls back to `400 (Regular.ttf)`.
- `h1` requests **`font-weight: 700`**, which is available → **`Bold.ttf` is used**.
- `p` requests **`font-style: italic`**, which exists → **`Italic.ttf` is used**.


## 4.  **size-adjust** Default(100%)

**`size-adjust` makes the custom font bigger or smaller, so when it replaces the fallback text, it matches the fallback size more closely and doesn't cause visible shifting.**


### Example:

```css
@font-face {
  font-family: 'MyFont';
  src: url('MyFont.woff2') format('woff2');
  size-adjust: 96%;
}
```

This means:

> Scale the custom font down to **96%** of its original size so it sits comfortably in place of the fallback font without making text lines jump.



## 5. Unicode-range default (all available language in the glyphs) && woff2


1. **WOFF/WOFF2 compression:**  
    They compress font files (like `.ttf` or `.otf`) to make them smaller and faster to load.  
    Think of it like zipping your clothes for travel — it’s still all the same items but tightly packed.
    
2. **Multiple languages in one font file:**  
    One `.woff2` file can contain glyphs for multiple languages (e.g., Latin, Greek, Cyrillic).  
    If the browser downloads that file, it brings all those glyphs at once, whether they’re needed or not — unless the file itself is subsetted to just one language.
    
3. **Unicode-range usage:**  
    The browser first looks at the  text content of the webpage and then checks the defined unicode-range blocks in your @font-face.

   It will only download the font file that matches the unicode ranges required for the characters present on the page.

   *This is an optimization step, so the browser doesn't waste bandwidth downloading glyphs that will never be used.
 
>If text is not found in the Unicode-range is fallback to the font stack.
    

- If you have three glyphs languages in the font file in `@font-face`  — one for Latin glyphs, one for Greek, one for Cyrillic —
- The browser will only download the Greek file if Greek letters appear in the text.
- If no Greek letters appear, it skips that file entirely.


## Why include `format` in the src property 


If you list multiple font files in the `src` property of your `@font-face` rule **without specifying `format()`**, the browser **may** try to download **all the font files** (listed in the `src`), as it won't have a clear indication of which format is best suited for it. After downloading all the files, it will attempt to use the **first one** that it successfully loads and can render.

Here’s what happens:

### Scenario:

```css
@font-face {
  font-family: 'MyFont';
  src: url('MyFont.woff2'),
       url('MyFont.woff'),
       url('MyFont.ttf');
}
```

Without specifying `format()`, the browser will:

1. **Download all three font files** (`MyFont.woff2`, `MyFont.woff`, `MyFont.ttf`).
2. **Try to use the first font** that successfully loads and is supported. If `MyFont.woff2` loads successfully, it will use that. If not, it will move to the next file, `MyFont.woff`, and so on.

This means:

- The browser **might download extra files** that aren't necessary.
- It could slow down the page load, especially if it tries to download more fonts than needed.

### Why `format()` matters:

When you add the `format()` function for each font, you're providing the browser with a clear hint about what kind of file it’s about to download. The browser can then immediately **skip** files that it knows it can't handle, and it'll **download only the relevant font format**.

For example:

```css
@font-face {
  font-family: 'MyFont';
  src: url('MyFont.woff2') format('woff2'),
       url('MyFont.woff') format('woff'),
       url('MyFont.ttf') format('truetype');
}
```

With `format()`, the browser knows exactly which file to use and will only download the relevant ones, minimizing unnecessary downloads and improving performance.
