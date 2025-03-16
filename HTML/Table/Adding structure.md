### Adding structure with `<thead>, <tbody>, and <tfoot>
As your tables get a bit more complex in structure, it is useful to give them more structural definition. One clear way to do this is by using `<thead>, <tbody>, and <tfoot>,` which allow you to mark up a header, body, and footer section for the table.

These elements don't necessarily make the table any more accessible to screen reader users. They don't result in any visual enhancement on their own, 

However they are very useful for applying styling and layout enhancements via CSS, which can improve accessibility. To give you some interesting examples, in the case of a long table you could make the table header and footer repeat on every printed page, and you could make the table body display on a single page and have the contents available by scrolling up and down.

- The `<thead>` element must wrap the part of the table that is the header — this is usually the first row containing the column headings, but this is not necessarily always the case. If you are using [`<col>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/col)/[`<colgroup>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/colgroup) elements, the table header should come just below those.

- The `<tbody>` element needs to wrap the main part of the table content that isn't the table header or footer.

- The `<tfoot>` element needs to wrap the part of the table that is the footer — this might be a final row with items in the previous rows summed,

*Code preview on how to apply `thead, tbody, and tfoot
https://github.com/mdn/learning-area/blob/main/html/tables/advanced/spending-record-finished.html

**Note:** `<tbody>` is always included in every table, implicitly if you don't specify it in your code.