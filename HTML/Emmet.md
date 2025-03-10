It's a built in plug-in in VS code that provides shortcut for writing code.

### Abbreviations Syntax
Emmet uses syntax similar to CSS selectors for describing elements’ positions inside generated tree and elements’ attributes.

### Elements
You can use elements’ names like div or p to generate HTML tags. Emmet doesn’t have a predefined set of available tag names, you can write any word and transform it into a tag: div → <div></div>, foo → <foo></foo> and so on.

### Nested Operator 
Nesting operators are used to position abbreviation elements inside generated tree: whether it should be placed inside or near the context element.

#### child: >

It is use > operator to nest elements inside each other:

**This emmet
`div>ul>li`

**Will produce this...
`<div>
``    <ul>
``        <li></li>
    `</ul>
`</div>`

### Sibling: +

Use + operator to place elements near each other, on the same level:

**This emmet**
`div+p+bq`

**Will produce this...**

`<div></div>
`<p></p>`
`<blockquote></blockquote>`

### Climb-up: ^
The `^` operator, climb one level up the tree and becomes the sibling to the element.

**This emmet**
`div+div>p>span+em^bq`

**Will produce this...**
`<div></div>
`<div>
`  <p><span></span><em></em></p>
   `<blockquote></blockquote>`
`</div>`

### Multiplication: `*`
It defines how many times element should be generated.

**This Emmet**
`div#container>ul>li*3`

**Will produce this**
`<div id="container">
``    <ul>
``        <li></li>
        `<li></li>
         `<li></li>
    `</ul>
`</div>`

#### How to convert the existing text to a list.

`About
`News
`Products
`Contacts`

**This Emmet**
 `ul>li*`

**Produce this...**
`<ul>
``    <li>About</li>

    <li>News</li>
``    <li>Products</li>

    <li>Contacts</li>
`</ul>`


### When list text is copied from MS Word they are contain with bullet or numbering, 
###### *How to remove the bullet or numbering?*

`|t`

The pipe `|` and the `t` is used to remove the bullet and numbering.

**This Emmet**
`ul>li*|t`

**Makes this**
- one
- two
- three

**To be this...** As it removes the bullet or numbering 
`<ul>
    `<li>One</li>`
    `<li>Two</li>`
    `<li>Three</li>`
`</ul>`

### Grouping : ()
It is used to group element 

**This Emmet** 
`div>(header>h1)+footer`

**Will produce this...**
`<div>`
   `<header>`
      `<h1></h2>`
   `</header>`
   `<footer></footer>`
`</div>`

### Attributes: [ ]
It is use to add square attributes to element.

**This Emmet**
`a[href="www.google.com"]`

**Will produce this...**
`<a href="www.google.com"></a>`

### Text content: { }
It is use to define the text content of an element 

**This Emmet**
`p{God is merciful}`

**Will produce this**
`<p>God is merciful</p>`

*A more complex example for {}*
`p{Click}` and `p>{Click}` produces the same output 

`<p>Click</p>`

As such `p>{Click} + a{here}` is `<p> Click <a href=""> here </a></p>`

Because `a`  element become the sibling to the `p` text content which it contain.

**This Emmet**
`p>{Click} + a{here} + {Continue}`

**Will produce this...**
`<p> Click <a href=""> here </a> Continue</p>`

### Numbering: $
It is used to insert number in a element or attributes.

**This Emmet**
`p.item-$*2`

**Will produce this**
`<p class="item-1"></p>`
`<p class="item-2"></p>`

### Assigning two class or ID to an element 

**This Emmet**
`.classOne.classTwo`

**Will produce this**
`<div class="classOne classTwo"></div>`


### Adding Multiple Numbering : $

**This Emmet**
`ul>li.item$$$*2`

**Will produce this...**

`<ul>`
 `<li class="item001"></li>`
 `<li class="item002"></li>`
 `<li class="item003"></li>`
`</ul>`

### Change Numbering Direction to Descending order : @-

**This Emmet*#
`.item$@-*2`

**Will produce this**
`<div class="item2"></div>`
`<div class="item1"></div>`

### To modify where numbering begin from :@N

**This Emmet**
`.item$@3*2` // Begin at numbering from 2 and create two elements.

**Will produce this**
`<div class="item3"></div>`
`<div class="item4"></div>`

### To modify where numbering begin from and arrange it in descending other : @-3

**This Emmet**
`.item$@-3*2` // Begin at numbering from 2 and create two elements.

**Will produce this**
`<div class="item4"></div>`
`<div class="item3"></div>

### To modify element type

**This Emmet**
`input:checkbox`

**Will produce this...**
`<input type="checkbox"/>`

### Short key to select element in the same tree level

**Ctrl +D**
