

## The CSS @font-face Rule

Web fonts allow Web designers to use fonts that are not installed on the user's computer.

When you have found/bought the font you wish to use, just include the font file on your web server, and it will be automatically downloaded to the user when needed.

Your "own" fonts are defined within the CSS `@font-face` rule.

---

## Different Font Formats

**TrueType Fonts (TTF)**

TrueType is a font standard developed in the late 1980s, by Apple and Microsoft. TrueType is the most common font format for both the Mac OS and Microsoft Windows operating systems.

**OpenType Fonts (OTF)**

OpenType is a format for scalable computer fonts. It was built on TrueType, and is a registered trademark of Microsoft. OpenType fonts are used commonly today on the major computer platforms.

**The Web Open Font Format (WOFF)**

WOFF is a font format for use in web pages. It was developed in 2009, and is now a W3C Recommendation. WOFF is essentially OpenType or TrueType with compression and additional metadata. The goal is to support font distribution from a server to a client over a network with bandwidth constraints.

**The Web Open Font Format (WOFF 2.0)**

TrueType/OpenType font that provides better compression than WOFF 1.0.

**SVG Fonts/Shapes**

SVG fonts allow SVG to be used as glyphs when displaying text. The SVG 1.1 specification define a font module that allows the creation of fonts within an SVG document. You can also apply CSS to SVG documents, and the @font-face rule can be applied to text in SVG documents.

**Embedded OpenType Fonts (EOT)**

EOT fonts are a compact form of OpenType fonts designed by Microsoft for use as embedded fonts on web pages.


*IE: The font format only works when set to be "installable".

## Using The Font You Want

In the `@font-face` rule; first define a name for the font (e.g. myFirstFont) and then point to the font file.

> **Tip:** Always use lowercase letters for the font URL. Uppercase letters can give unexpected results in IE.

To use the font for an HTML element, refer to the name of the font (myFirstFont) through the `font-family` property:

```css

@font-face {
  font-family: myFirstFont;
  src: url(sansation_light.woff);
}

div {
  font-family: myFirstFont;
}
```

## CSS Font Descriptors

The following table lists all the font descriptors that can be defined inside the `[@font-face](https://www.w3schools.com/cssref/atrule_font-face.php)` rule:

| Descriptor    | Values                                                                                                                                                       | Description                                                                                 |
| ------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------- |
| font-family   | _name_                                                                                                                                                       | Required. Defines a name for the font                                                       |
| src           | _URL_                                                                                                                                                        | Required. Defines the URL of the font file                                                  |
| font-stretch  | normal  <br>condensed  <br>ultra-condensed  <br>extra-condensed  <br>semi-condensed  <br>expanded  <br>semi-expanded  <br>extra-expanded  <br>ultra-expanded | Optional. Defines how the font should be stretched. Default is "normal"                     |
| font-style    | normal  <br>italic  <br>oblique                                                                                                                              | Optional. Defines how the font should be styled. Default is "normal"                        |
| font-weight   | normal  <br>bold  <br>100  <br>200  <br>300  <br>400  <br>500  <br>600  <br>700  <br>800  <br>900                                                            | Optional. Defines the boldness of the font. Default is "normal"                             |
| unicode-range | _unicode-range_                                                                                                                                              | Optional. Defines the range of UNICODE characters the font supports. Default is "U+0-10FFFF |
