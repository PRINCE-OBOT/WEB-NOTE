onerror is an event handler in JavaScript and HTML that fires when an error occurs.

____

`<img src="wrong-image.jpg" onerror="func()"> `

The `func()` runs the JavaScript function if image src is not found.

### onerror
________________

`<img src="wrong-image.jpg" onerror="this.src='fallback.jpg';">

`This` serve as a fallback when the initial image src is not found.

___

`<img src="wrong-image.jpg" onerror="alert(myName)">

This `alert` the variable `myName` if image src is not found.

# Using JavaScript (error)

```
HTML
<img src="./shirt.jpg" />


<script>
const img = document.querySelector('img')

img.addEventListener('error', ()=>{
 alert('Hi')
})
//This event fires when the image fails to load
```