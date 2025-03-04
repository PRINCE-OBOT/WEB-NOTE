Helps for automatically displaying or executing the typed data immediately without having to click a button. **Fires when typing.

**HTML**
`  <input type="text" />
    <p></p>

**script**
```
const inp = document.querySelector("input")
const para = document.querySelector("p")
     
inp.addEventListener("input", (e)=>{
       para.textContent = e.target.value
     }) `
```