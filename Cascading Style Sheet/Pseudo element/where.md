The `:where` pseudo element has zero specificity and it also helps reduce redundancy.

It can also select multiple elements.`:where(one, two, ...)`


*Using the html code below for an example with revert*

```html

 <div class="div">
    <h1 class="h">This is the heading</h1>
 </div>
```

## Applying `revert` with `:where`

**Revert** is a value that returns an element to it user-agent style.

Before you can revert an element previous style make the specificity of the revert should be higher than the previous style or the same.

Using the HTML elements as the example.
*Trying to revert the color of h1*
If the previous selector was styled.

```css
h1{
color : red;
}
```

To revert it you need something higher, *not*
 `:where(h1)` since `:where` has zero specificity, the revert value will not be applied. So use something like ,

```css
div :where(h1){
all : revert;
}
```

And if you want to redefine the color, you can simply use selector the same as the selector inside the `:where` pseudo element `(h1)` or something higher `(.h)`.

```css
.h{
color : pink;
}
```