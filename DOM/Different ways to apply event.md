

# 1.
You can specify function attribute directly on HTML elements.

```
<button onclick="run()"> click me </button>
```

*You can access the **event** object by calling **event** from as a global variable in the function.

```
SCRIPT

function run(){
 alert('Hello world')
 
 console.log(event)
}
```


# 2.
You can set properties in the form of `on<eventType>` such as click, or mousedown on the DOM nodes in your JavaScript.

```
HTML

<button> click me </button>

SCRIPT

const btn = document.querySelector('button')

btn.onclick = ()=>{
alert('hi')
}
```

*You can access the **event** object by calling **event** from as a global variable in the function or passing a **parameter** to the function.

*This* (global)
```
btn.onclick = ()=>{
 console.log(event)
}
```

*Or this* (passing as a parameter)

```
btn.onclick = (e)=>{
 console.log(e)
}
```


# 3.

You can attach event listeners to the DOM nodes in your JavaScript.

HTML

```
<button> click me </button>

SCRIPT

const btn = document.querySelector('button')

btn.addEventListener("click", ()=>{
alert('hi')
})
```


You can access the **event** object by calling **event** as a global variable in the function or passing a **parameter** to the function.

*This* (global)
```
btn.addEventListener("click", ()=>{
 console.log(event)
})
```

*Or this* (passing a parameter)

```
btn.addEventListener("click", (e)=>{
 console.log(e)
})
```
