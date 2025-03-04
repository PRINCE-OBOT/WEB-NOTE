Inner HTML is used to display information on the web page using JavaScript.

It correctly represent information in the web page and it is also accept HTML tag.

`p.innerHTML = '<b>Bold</b>'`

but the side effect is when is `innerHTML` is used to display information from user via `input or prompt`.

*Example

If `<IMG src="" onerror="alert(password)" />` is entered in the `input or prompt`. innerHTML appends it in the DOM, while appending it, if the image src is not found `onerror` event handler fires and alert the variable `password` in the script.

**Summary** this is to say that user can access information in the script.