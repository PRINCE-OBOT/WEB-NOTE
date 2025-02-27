### Adding a caption to your table with `<caption>

You can give your table a caption by putting it inside a `<caption>` element and nesting that inside the `<table>` element. 

`<table>
  `<caption>
    Dinosaurs in the Jurassic period
 `</caption>
 // 
`</table>`

**Note:** The [`summary`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/table#summary) attribute can also be used on the `<table>` element to provide a description — this is also read out by screen readers. We'd recommend using the `<caption>` element instead, however, as `summary` is deprecated and can't be read by sighted users (it doesn't appear on the page)