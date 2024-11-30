## CSS Box Model

1. It can be use to inspect how much space an element takes up.

2. how far an element is from other element

## box-shadow

It returns three values
`box-shadow: 0 0 0 color`

**0**: The first zero edit how long the shadow on the horizontal axis should be from left to right.

**0**: The second zero edit how long the shadow on the vertical axis should be from top to bottom.

**0**: The third zero edit how blurry the shadow should be.

**color**: color of the shadow (it is best to use).
The above shadow values set the shadow outside the element, to set the shadow inside the element add _inset_ value
`box-shadow: inset 0 0 0 color`

## transition

`transition: property delay;`
It return two values

**property** This is the property to be delay (e.g background-color, color, opacity, box-shadow)

**delay** This is how long it takes for the transition to occur (it is measured in seconds)

## Browser Default

By default browser arranges our element base on text on the same line
`vertical-align: top`
The code above is use to overwrite the default alignment of the browser, making all element arrange using the actual element at the top

## img css properties

`object-fit:` it can be (contain, cover).
`object-position` it can be (top, bottom), it is used when the object-fit is set to _contain_

*The below code is use to fix and edit image using css and include opacity*
`.container{
      background: peachpuff;
      flex: 1;
      height: 100vh;
    }
    .container::before{
      background: url(./1.jpeg) no-repeat center/cover;
      //background: linear-gradient(to bottom, rgb(242, 48, 48,0.9), rgb(110, 10, 10, 0.9), rgb(3, 3, 76,0.9)) ;
      position: absolute;
      top: 0;
      bottom: 0;
      right: 0;
      left: 0;
      width: 100%;
      height: 100vh;
      content: "";
      color: rgb(39, 1, 1);
      background-color: black;
      z-index: 1;
    }`
## input

It can either be use as a checkbox`<input type="checkbox" name="" id="">` or a search bar
`<input type="text">`

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