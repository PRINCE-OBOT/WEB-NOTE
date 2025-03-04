Submit is an event that fires when the form is submitted.

It is used to submit user input in the form to the server for processing by **default**, this is why the page reloads. 

*It is important for the page to reloads as this make the submission process complete.

```
HTML
<form>
  <input type="text" />
  <button>Submit</button>
</form>

<script>
let myName = null
const form = document.querySelector('form')
const inp = document.querySelector('input')
form.addEventListener('submit', (e)=>{
  e.preventDefault() //Prevent the page from reloading, as so doing stop it from sending to the server.
  
  myName = inp.value
})
```

**But**, you can change the behaviour using `preventDefault()`

## Manually submitting form

```
 <form>
   <input type="text" /> 
  <button>Submit</button>
  </form>
<p>Check</p>
<script>

const inp = document.querySelector('input')
const form = document.querySelector('form')
const p = document.querySelector('p')

p.addEventListener('click', ()=>{
//The form is submitted when the p element is clicked

form.submit()
p.textContent = inp.value
})
```