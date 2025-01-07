It is used to determine when an element receive focus.

By default focusable element have the tab index of `0`, setting it to 1, means the tab index with `1` will receives focus only when all other elements and also the icon on the browser have received focus. And the tab index with `2` will receive focus when tab index `1` receives focus. 

**Note**: The higher the tabindex the longer it takes to receive focus.

It can also be use to make an element that is not focusable by default to be focusable.

Example 
`<div tabindex="0">Focusable now</div>`

