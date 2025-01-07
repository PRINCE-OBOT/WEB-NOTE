
## Grid

A grid is a layout with row and column.
_2 rows and 1 column_ is called **2 by 1** grid

In order to set grid, you will have to set the `display: grid`
Then you decide how many rows and column you want your layout to have by setting the `grid-template-columns: 100px 1fr`. The first value takes up **100px** space and the second value **1fr** takes up the remaining space

**Characteristics of grid**

1.  It only takes up the entire column measurement giving to it
2.  It is vertically align.
3.  It eliminate the default spacing of the browser.

### The main difference between a flexbox and grid

**flexbox** flexible layout.

**grid** rigid layout.

## Psuedo element

`button::active{color: red}`: it activate when the button is click.
`button::hover{color: red}`: it activate when you hover around the element.
`input::placeholder{font-size:23px}`: it is use to change the edit input placeholder.
`button::before{text-content: "Hi"}`: It is use to append text before the element.
`button::after{text-content: "Hi"}`: It is use to append text after the element.

## Position fixed: 
placed in the browser window.

## Position absolute: 
placed on the page.

## Position relative:
does not really change anything, it is useful when you want your absolute element to flexible while the page scroll.

## z -index
`z-index:0` has a default value of 0, any element with the higher z-index is placed above an element with the lower z-index.
**Note:** it only works for element that has the `position` property.
*and* when `position: absolute` element is placed inside of `position:fixed` element it behaves relative to the `position:fixed` dimension.

## Pointer event
`pointer-event: none` set the child inside an element not to delegate.
**This is applicable** when you don't want your overlay to obstruct any interaction with the element behind it.

`pointer-event: auto` this is the default behaviour, where you can clicked element behind the overlay.

## Media Query:
Media query simply means resizing the content of an element when it get a particular size in other to maintain visibility.
    .content{
        display: grid;
        grid-template-columns: 1fr 1fr 1fr;
        column-gap: 10px;
        row-gap: 10px;
      }

      @media (max-width:700px){
        .content{
          grid-template-columns: 1fr 1fr;
        }
      }`
`
## Semantics element
This element perform the same purpose as the div just that it enhances search engine and screen readers.

`header` for top
 `nav` for element that's redirects you to different area of the webpage
 `main` for the body  
 `section` should be contain inside the `main`
 `footer` should be placed below the webpage.

 ## Inheritance
Not all styles are inherited by the child element.
styles inherited by the element are, font-family, color, font-weight, font-size.