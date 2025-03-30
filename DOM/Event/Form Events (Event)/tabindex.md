tabindex is an HTML attribute that controls the keyboard navigation order of an element when pressing the Tab key.

By default, only interactive elements like;
`<a>,
`<button>,
`<input>, 
`<textarea>`

can be focused. But with tabindex, you can make any non-focusable element focusable and control its order.

## How to make non-focusable element focusable

```html

//The p element becomes focusable.
<p tabindex="0">Now focusable</p>
```

---

## How tabindex Works

___
tabindex="0" (Default Flow)

 It follows the normal DOM order (left to right, top to bottom).

___
tabindex="1" (Highest priority)

___
 tabindex="2" (Follows in ascending other immediately after 1) and so on...

## Unexpected behaviour of tabindex.

**When you click on the screen the tabindex  changes from it expected behaviour.

what the happens?
1. The first element get focused first regardless of it tabindex.

2. Element with `tabindex` 0 get focused, following the normal progression.

3. All navigation button at the top of the browser get focused.

4. Before the element with `tabindex` 1 get focus

5. If there are other positive number like 2, then it get focus next, and so on...

## negative tabindex 

tabindex="-1" do not get focused with tab index, you can use it if you want to the element to get focused programmatically using the `focus()` event handler.

```html

<p tabindex="-1">Focus programmatically</p>

<Script>
document.querySelector('p').focus

//The p tag get focused automatically without using the tabindex
```

## Normal behavior with negative tabindex 

1. When element with negative tabindex is been focus programmatically, (the element automatically get focus)

2. Next element to get focused when the tab index is pressed is element with `tabindex` 1.

3. Next to other positive number arranged in ascending order(2, 3) and so on...

4. The falls back to tabindex with 0.

## Unexpected behaviour of negative tabindex 

**When you click on the screen the tabindex  changes from it expected behaviour.

1. tabindex with positive number greater than 1, get focused first and progresses in ascending order.

2. Then falls back to tabindex with 0

3. All navigation button at the top of the browser get focused.

4. Then `tabindex with 1` get focused


**Note** only one element get focused at a time.

*If two elements has the tabindex of -1, only one element get the focus programmatically.
