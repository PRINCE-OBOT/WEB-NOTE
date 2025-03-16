
The `text-transform` property in CSS controls the capitalization of text. It has several values:

1. `none` – The text appears as it is in the HTML (default behavior).
2. `uppercase` – Converts all letters to uppercase.
3. `lowercase` – Converts all letters to lowercase.
4. `capitalize` – Capitalizes the first letter of each word.
5. `full-width` – Converts characters to their full-width form, mainly for East Asian typography.
6. `full-size-kana` – Affects Japanese kana characters, converting half-width kana to full-size kana.

>`full-width` and `full-size-kana` is bearly supported by **most** browser.


```css
p.upper { text-transform: uppercase; }
p.lower { text-transform: lowercase; }
p.cap { text-transform: capitalize; }
```

```html
<p class="upper">This is uppercase text.</p>
<p class="lower">THIS IS LOWERCASE TEXT.</p>
<p class="cap">this is capitalized text.</p>
```
