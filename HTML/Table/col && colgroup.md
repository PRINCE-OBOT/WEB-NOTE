In an HTML table, the `<col>` element is used to define column properties for one or more columns. It enclosed `<colgroup>` element to apply styling or attributes to entire columns instead of setting them individually on each `<td>` or `<th>.


## Accepted Properties

1. width → Sets the width of the column.

2. visibility → Hides the entire column without removing it from the layout. `visibility : collapse;`

3. background / background-color → Changes the background of all cells in the column.

4. border → Affects the border of the entire column (but behavior varies across browsers).

*The **col** is semantically enclosed with **colgroup

`<colgroup>
  `<col>`
  `<col>`
  `<col>`
      `<tr>` // point to col 1
      `<tr>` // point to col 2
      `<tr>` // point to col 3
`</colgroup>`