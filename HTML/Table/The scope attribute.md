The `<th>` tag defines a header, but the **scope attribute** removes ambiguity, making tables more accessible and correctly interpreted by assistive technology.

**Scope attributes values

• col
• row
• colgroup
• rowgroup 

**col and row** 
Are used for single column heading or heading that sit below the upper heading.

**colgroup and rowgroup**
are used for headings that sit over the top of multiple columns or rows.(The first-top heading)

`<thead>
  `<tr>
    `<th scope="col">Purchase</th>
    `<th scope="col">Location</th>
    `<th scope="col">Date</th>
    `<th scope="col">Evaluation</th>
    <th scope="col">Cost (€)</th>
  `</tr>
`</thead>
