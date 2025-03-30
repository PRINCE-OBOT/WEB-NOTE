### Improve line wrapping

When there are too many words to fit on a single line of text, the default behaviour is to push any words that don’t fit onto the next line. This process is repeated until none of the lines overflow:

This algorithm works well enough most of the time, but it sometimes produces awkward results. My least favourite example is when a paragraph ends with an emoji, and that emoji is pushed to its own line:

To solve this problem, we can opt into an alternative line-wrapping algorithm with the new `text-wrap` property!

For paragraphs, I use the `pretty` option. This algorithm will make sure that the final line of text has at least two words. It also makes other subtle tweaks to improve the visual balance of the paragraph:

```CSS

.box{
   text-wrap : pretty;
}
```

# other text-wrap property


1. **"wrap (default)** – Text wraps normally according to the container’s width.

2. **nowrap** – Prevents text from wrapping; text stays in a single line and may overflow.

3. **balance** – Tries to distribute text across multiple lines as evenly as possible.

4. **pretty** – A more advanced version of balance that optimizes line breaks for aesthetics.

5. **stable** – Ensures consistent wrapping even if content changes dynamically.



