The `hyphens` property in CSS controls how words are broken at line breaks. It has the following values, it's more intuitive when `overflow-wrap` is set.

1. **`none`** – Prevents hyphenation, even if the word would normally break.

2. **`manual`** – Allows hyphenation only where there are soft hyphens (`&shy;`) in the text.

3. **`auto`** – Allows the browser to automatically hyphenate words according to the language’s hyphenation rules.

```css

.box{
  hyphens: auto;
}

```

4. **`all`** (CSS Text Module Level 4) – Allows hyphenation even in the middle of words, without following traditional rules.

5. **`inherit`** – Takes the hyphenation setting from the parent element.

6. **`initial`** – Resets the property to its default value (`manual`).

7. **`unset`** – Removes the property; acts as `inherit` if it has a parent value, otherwise acts as `initial`.

