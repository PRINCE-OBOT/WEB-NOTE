


## Variable fonts 

Variable fonts are single font files that contain multiple variations of weight, width, slant, or other properties instead of separate font files for each style (bold, italic, etc.).


1. **For a variable font in `.ttf` format:**  
    You must use:
    

```css
format("truetype-variations")
```

This tells the browser that it’s a TrueType font with variable capabilities.

> Why? Because older browser engines may not guess that a `.ttf` file contains variations without that specific format hint.

2. **For a variable font in `.woff` or `.woff2` format:**  
    You just use:
    

```css
format("woff")  // for woff
format("woff2") // for woff2
```

> Why? The browser already knows that `.woff` and `.woff2` formats can contain variations — no extra hint needed.


# Values of variable font


**Font-weight (wght)**:  
This axis controls how bold or light the text is. The range (like 100–900 or 0–205) is set inside the font file. The higher the value, the thicker the letters. If the font supports variable weights, you can smoothly adjust boldness with `font-variation-settings: 'wght' value;`.

**Font-width (wdth)**:  
This axis controls how wide or narrow the letters appear. The value is usually from around 50 (very narrow) to 200 (very wide). Setting `font-variation-settings: 'wdth' value;` lets you stretch or compress text width without changing the font size.

**Ital (italic axis)**:  
If present, this axis controls whether the text is upright (`0`) or italic (`1`). Some fonts also use `slnt` (slant) to tilt the letters at a certain angle. If the font doesn’t have this axis, you either use `font-style: italic;` or load an italic font variant.



```css

@font-face {
  font-family: 'RobotoFlex';
  src: url('RobotoFlex-VariableFont_wght.woff2') format('woff2');
  font-weight: 100 900; /* covers weights from 100 to 900 */
}
```


>**[[https://wakamaifondue.com]] is a website used to check range of a particular font file range of `font-weight(wght), font-stretch(wdth)`, or support `ital`.



# Axis

In a variable font, an axis means that a certain property (like weight) can be adjusted continuously between a minimum and maximum value. If the font supports that axis, then yes — you can control it using font-variation-settings.

    

## `font-variation-settings` && `font-weight:100 900;`



When you see this inside `@font-face`:

```css
@font-face {
  font-family: 'MyFont';
  src: url('myfont.woff2') format('woff2');
  font-weight: 100 900;
}
```

It means:

> "This font file supports a continuous range of weights between 100 and 900."

Now, **why do this?**  
Because after telling the browser that the font supports this range, you can simply use `font-weight` on your elements:

```css
h1 {
  font-family: 'MyFont';
  font-weight: 700;
}
p {
  font-family: 'MyFont';
 }

```


***Or 


You use `font-variation-settings` to manually control these axes and get fine-tuned control over text appearance.

- Without using it, the browser may pick default values, and you lose that flexibility.



```css

font-variation-settings: 'wght' 800, 'wdth' 75, 'ital' 1;

```
