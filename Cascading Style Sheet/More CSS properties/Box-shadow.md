
The **`box-shadow`** [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property adds shadow effects around an element's frame. You can set multiple effects separated by commas. A box shadow is described by X and Y offsets relative to the element, blur and spread radius, and color.



The `box-shadow` property enables you to cast a drop shadow from the frame of almost any element. If a [`border-radius`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-radius) is specified on the element with a box shadow, the box shadow takes on the same rounded corners. The z-ordering of multiple box shadows is the same as multiple [text shadows](https://developer.mozilla.org/en-US/docs/Web/CSS/text-shadow) (the first specified shadow is on top).



## Specify a single box-shadow using:

- Two, three, or four [`<length>`](https://developer.mozilla.org/en-US/docs/Web/CSS/length) values.
    
    - If only two values are given, they are interpreted as `<offset-x>` and `<offset-y>` values.
    
	- If a third value is given, it is interpreted as a `<blur-radius>`.
    
	- If a fourth value is given, it is interpreted as a `<spread-radius>`.
       
>*Positive values will cause the shadow to expand and grow bigger, negative values will cause the shadow to shrink. If not specified, it will be set to `0` (that is, the shadow will be the same size as the element).
     
- Optionally, the `inset` keyword.

>*Changes the shadow from an outer box-shadow to an inner box-shadow (as if the content is pressed into the box). 
    
- Optionally, a [`<color>`](https://developer.mozilla.org/en-US/docs/Web/CSS/box-shadow#color) value.

> *`<color>` specifies color for the shadow. See `<color>` values for possible keywords and notations. If not specified, the value of the color property defined in the parent element is used


## Multiple shadow 

```css

box-shadow: 5px 5px 0px #f00, -30px -2px 5px olive;
```