
### Table element 

|Element|What it is|
|---|---|
|`<table>`|The table itself|
|`<caption>`|The caption for the table. Like a figcaption to a figure.|
|`<thead>`|The table header|
|`<tbody>`|The table body|
|`<tfoot>`|The table footer|
|`<tr>`|A table row|
|`<th>`|A table cell that is a header|
|`<td>`|A table cell that is data|
|`<col>`|A column (a no-content element)|
|`<colgroup>`|A group of columns|

### All Table Related Attributes

|Attribute|Element(s) Found On|What it does|
|---|---|---|
|`colspan`|th, td|extends a cell to be as wide as 2 or more cells|
|`rowspan`|th, td|extends a cell to be as tall as 2 or more cells|
|`span`|col|Makes the column apply to more to 2 or more columns|
|`sortable`|table|Indicates the table should allow sorting. **UPDATE:** I’m told this was removed from spec because of lack of implementations.|
|`headers`|td|space-separated string corresponding to ID’s of the `<th>` elements relevant to the data|
|`scope`|th|row \| col \| rowgroup \| colgroup (default) – essentially specifies the axis of the header. The default is that a header is heading a column, which is typical, but a row might start with a header also, where you would scope that header to the row or rowgroup.|

### Important Style Rules for Tables

| CSS Property    | Possible values                                                                                                 | What it does                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| --------------- | --------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| vertical-align  | baseline  <br>sub  <br>super  <br>text-top  <br>text-bottom  <br>middle  <br>top  <br>bottom  <br>%  <br>length | Aligns the content inside a cell. Works particularly well in tables, although only the top/bottom/middle make much sense in that context.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| white-space     | normal  <br>pre  <br>nowrap  <br>pre-wrap  <br>pre-line                                                         | Controls how text wraps in a cell. Some data may need to be all on one line to make sense.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| border-collapse | collapse  <br>separate                                                                                          | Applied to the table to determine if borders collapse into themselves (sort of like margin collapsing only bi-directional) or not. What if two borders that collapse into each other have conflicting styles (like color)? The styles applied to these types of elements will “win”, in order of “strength”: cell, row, row group, column, column group, table.                                                                                                                                                                                                                                                          |
| border-spacing  | length                                                                                                          | If `border-collapse` is `separate`, you can specify how far cells should be spaced out from each other. Modern version of `cellspacing` attribute. And speaking of that, `padding` is the modern version of the `cellpadding` attribute.                                                                                                                                                                                                                                                                                                                                                                                 |
| width           | length                                                                                                          | Width works on table cells just about how you would think it does, except when there is some kind of conflict. For instance if you tell the table itself to be 400px wide then the first cell of a three-cell row to be 100px wide and leave the others alone, that first cell will be 100px wide and the other two will split up the remaining space. But if you tell all three of them to be 10000px wide, the table will still be 400px and it will just give each of them a third of the space. That’s assuming white-space or elements like an image don’t come into play. This is probably a whole post in itself! |
| border          | length                                                                                                          | Border works on any of the table elements and just about how you would expect. The quirks come in when you collapse the borders. In this case all table cells will have only one border width between them, rather than the two you would expect them to have (border-right on the first cell and border-left on the next cell). In order to remove a border in a collapsed environment, both cells need to “agree” to remove it. Like `td:nth-child(2) { border-right: 0; } td:nth-child(3) { border-left: 0; }` Otherwise, source order/specificity wins which border is shown on which edge.                          |
| table-layout    | auto  <br>fixed                                                                                                 | `auto` is the default. The width of the table and its cells depends on the content inside. If you change this to `fixed`, equal width is distributed among the data cell. **Note** You must provide the `width` of the table and the `table-layout : fixed;` is always applied to the `table` element.                                                                                                                                                                                                                                                                                                                   |

### The Table Stack

![[Pasted image 20250226110023.jpg]]
What this image means is, **table data** styling for `background color` will always overwrite **table** style as **table data** is on top.

### Default Styles / User Agent Stylesheet

`table { display: table; border-collapse: separate; border-spacing: 2px; border-color: gray } 

`thead { display: table-header-group; vertical-align: middle; border-color: inherit } 

`tbody { display: table-row-group; vertical-align: middle; border-color: inherit }

`tfoot { display: table-footer-group; vertical-align: middle; border-color: inherit } 

`table > tr { vertical-align: middle; } 

`col { display: table-column } 

`colgroup { display: table-column-group } 

`tr { display: table-row; vertical-align: inherit; border-color: inherit } 

`td, th { display: table-cell; vertical-align: inherit }

`th { font-weight: bold } caption { display: table-caption; text-align: -webkit-center }
## Other Explanation 

## [What is a table?](https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/Structuring_content/HTML_table_basics#what_is_a_table)

A table is a structured set of data made up of rows and columns (**tabular data**). A table allows you to quickly and easily look up values that indicate some kind of connection between different types of data, for example a person and their age, or a day of the week, or the timetable for a local swimming pool.

### Why is it a bad idea to use HTML table for page layout 

Using tables for layout in HTML is a bad idea because it goes against modern web development best practices. Here’s why:

1. **Not Semantically Correct** – Tables are meant for tabular data, not for structuring a webpage. Using `<table>` for layout confuses browsers, search engines, and assistive technologies like screen readers.
    
2. **Poor Accessibility** – Screen readers read tables row by row, making it harder for visually impaired users to navigate a layout built with tables.
    
3. **Difficult to Maintain** – If you need to modify the design, you’ll have to update multiple `<td>` and `<tr>` elements instead of just adjusting CSS.
    
4. **Not Responsive** – Tables do not adapt well to different screen sizes, making them a nightmare for mobile responsiveness compared to using CSS Grid or Flexbox.
    
5. **Slower Page Load** – Tables require more HTML and nested elements, increasing page size and slowing down rendering.
    

### When Should You Use Tables?

Tables are fine for displaying **tabular data**, like spreadsheets, schedules, or reports. If you're structuring a layout, it's better to use **CSS (Flexbox or Grid)** instead.

Do you want an example comparing a table-based layout with a modern CSS layout?
## caption

The `<caption>` element in an HTML table is used to provide a title or description for the table. It helps users understand what the table is about. By default, the caption is displayed above the table, but you can style it using CSS to change its position.

### Example:

```html
<table border="1">
  <caption>Student Grades</caption>
  <tr>
    <th>Name</th>
    <th>Math</th>
    <th>Science</th>
  </tr>
  <tr>
    <td>Alice</td>
    <td>90</td>
    <td>85</td>
  </tr>
  <tr>
    <td>Bob</td>
    <td>80</td>
    <td>88</td>
  </tr>
</table>
```

---

**colspan** default is 1, if increased it merge the column by the number of the value provided.

**rowspan** default is 1, if increased it flexes the row below to align next to it.