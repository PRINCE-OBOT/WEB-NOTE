Stands for **Scalable Vector Image**, it uses Math formula to generate images.
SVGs are a scalable image format, which means they will easily scale to any size and retain their quality without increasing their filesize.

### SVGs are often used for:

1. Icons
2. Graphs/Charts
3. Large, simple images
4. Patterned backgrounds
5. Applying effects to other elements via SVG filters

### SVGs are defined using:
XML. XML (aka, “Extensible Markup Language”) is an HTML-like syntax which is used for lots of things, from **APIs**, to **RSS**, to **spreadsheet and word editor software**.

### Benefit of SVG 
The fact that SVG source-code is XML has a few key benefits.

1. it means that it is human-readable.

2. XML is designed to be interoperable with HTML, which means you can put the above code directly in an HTML file, without any changes, and it should display the image. 

### Drawbacks
Since XML is use to generate SVG images, it is extremely inefficient for creating a more realistic photo or a grunde texture image.

### Anatomy of an SVG (The structure that make-up SVG)

1. **xmlns** : This is a XML namespace that tells the browser to interpret it as SVG image. Without it, some browsers will not render your image or will render it incorrectly.

2. **viewBox** :  It controls the overall dimensions and scaling of the SVG.

3. **class, id** - these attributes function just like they do in HTML. Using these in SVGs allows you to easily target an element via CSS or JavaScript, or to reuse an element via the use element.

4. **Use**: it is used to reused an existing element, like shape or group of shape by referencing to the original element, instead of repeating the code.

5. Elements such as <circle>, <rect>, <path>, and <text> are defined by the SVG namespace. Meaning that the element are valid and recognise within an SVG environment.
