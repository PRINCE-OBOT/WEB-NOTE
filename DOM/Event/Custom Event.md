Apart from having the chance to create your own event using custom event. Custom event also allows you to send various information across the webpage with the event object properties `detail`.

```
let myEvent = new  CustomEvent('click', {
   detail : {
     text : 'Winner!'
   }
 })
btn.addEventListener("click", (e)=>{
p.textContent = e.detail.text
})

btn.dispatchEvent(myEvent);
```

  **Note** the text `p` only have access to the **detail** information when the event is dispatched.