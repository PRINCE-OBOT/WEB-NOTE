



### focusout
Fires when you focus out of the input or selected textarea and it bubbles up to the DOM, meaning it propagate.

### blur
Fires when you focus out of the input, but it does not propagate.

` <input type="text" />

    <p style="display: none">Enter email</p>
    
    
      const inp = document.querySelector("input")
      const para = document.querySelector("p")
      const button = document.querySelector("button")
     
  
    inp.addEventListener("focus", (e)=>{
      para.style.display = "block"
    })`
**Note** : most focus events could be replaced with mouse event but, focus event also respond while the keyboard `tab` is been used to navigate around the input field, whereas mouse event only function using the mouse events.

**Using focus event to do `tooltip`** 
` <input type="text" />
    <p style="display: none">Enter email</p>
    <p style="display:none">Email valid info</p>
    
      const inp = document.querySelector("input")
      const para = document.querySelector("p")
      const button = document.querySelector("button")
    inp.addEventListener("focus", (e)=>{
      para.style.display = "block"
    })
    inp.addEventListener("blur", ()=>{
      setTimeout(()=>{
        
      para.style.display = "none"
      }, 2000)
    })  
`
### change event
Fires when an input value changes and losses focus

`inp.addEventListener("change", ()=>{
`p.textContent = inp.value  
})`
### form event
The form event allows for using the button it contain to submit the input information.
By default a button is set to submit `<button>Submit</button>` when inside of a form, if the type is not explicitly set to`<button type="submit">Submit</button>`if the type is explicitly set to button`<button type="button">Button</button>` then it does not submit information in the form, it can be set to perform other actions.

The addEventlistner is set on the form.
In other to prevent the form from refreshing each time information is submit you could `e.preventDefault()`
### animation event
It has three life cycle 
1. animationstart : tells when the animation start
2. animation iteration : tells the animation is in process.
3. animationend : tells the animation ended.

Animation is a CSS styling property, which by adding JavaScript animation events makes it more interactive.

Example.
You could write a code with JavaScript to perform an action when an animation in CSS starts, iterates or end.

**Style**
`  @keyframes mymove{
      from{scale: 1;}
      to{scale: 4;}
    }
  /*  @keyframes mymove{
      from{top: 0px;}
      to{top: 100px;}
    } */
    
 /* @keyframes mymove{
     from{color: red;}
      to{color: blue;} // you can also specify `from` as `0%`  - `to` as `100%`
    }
    */
/* * @keyframes mymove {
  0% { transform: translateX(0) scale(1); }
  100% { transform: translateX(100px) scale(1.5); }
  //With the transform keyword the code move from 0px from the x-axis to 100px of the x-axis
} */*

    
    #animate-btn{
    animation: mymove 2s cubic-bezier(0.68, -0.55, 0.27, 1.55) infinite; 7;
    position: absolute;
    }
    `
**HTML**
`<button>Click Me</button>`

This is just a simple animation that tells button how it will be move around the windows.

### Timing Function 
By default timing function is set to `ease in` animation but but you can explicitly specify how the timing function should be.
1. ease :  is it begins slowly, fast in the middle, then slow down when getting to the ending.
2. ease-out : it begins fast and get slower at the ending.
3. ease-in: begin slow and get faster at the ending.
4. ease-in-out : start slowly, speed in the middle and slow again at the ending, just like `ease` but provide more smoother transition from the beginning to the middle and the end
5. cubic-bezier : it's just a way of specify your own timing function. It has 4 parameters, (x1 y1 x2 y2)
   With values ranging from 0 - 1,
   Where 0 means fast
   And 1 means slow.
    *note* : it values can still be manipulated depending on how fast the animation should be.
**y1** : means how fast it should start from the beginning. 
x1 : how fast it should be when the animation begin. 

*@keyframe* specify the animation range. It is followed by a keyword that references which elements takes the animation.

`#animation-btn` it is just an `id` giving to the button element, where the animation is specify with many other properties. `animation: mymove 2s 7 alternate `

animation-name: The first parameter is the keyword that will be referenced to the keyframe so as to apply the animation range to it. It could be any name of your choice.

animation-delay : The second parameter tells the speed of the transition.

animation-count: The third parameter tells how many times the transition should occur. In this case it is `7` times, you can make it run infinitely by specifying `infinite`

animation-play-state: Allows you to pause or play the animation.

animation-direction: maintain the movement of the animation for both forward and reverse direction.`alternate`

*Applying JavaScript could help with interactive action while these animation is activated.*

**JavaScript**
`const btn = document.querySelector("button")
   const p = document.querySelector("p")
   
   btn.addEventListener("click", (e)=>{
     let clickBtn = e.target
   btn.classList.toggle("animate-btn") 
   clickBtn.addEventListener("animationstart", ()=>{
     p.textContent = "Start"
   }) 
   clickBtn.addEventListener("animationiteration", ()=>{
     p.textContent ="Iteration"
   })
   clickBtn.addEventListener("animationend", ()=>{
     p.textContent ="end"
   })
   })`

The JavaScript code specify information that will be displayed in each life cycle of the animation using the `p`  element.
# Keyboard Events

These are events that fires when the keyboard is been pressed
## Three main keyboard events
**keydown:** fires as long as the keyboard is been held.
**keyup:** fires when the keyboard is release.
**keypress:** fires when you release the keyboard.

## Two main properties of keyboard events

**key**: display the key press

**code**: displays "key" with the key pressed. e.g if key "G" is pressed it displays like (keyG)

**Note:** keydown and keypress continues to fire as long as the keyboard is been held
keydown and keyup provides keyboard property information for all keys whereas keypress provide information for the keyboard characters i.e a, b, ...z & 0, 1, 2 ...9

# Event Constructors

It is use to fire event without using the regular mouse click and keyboard event
Event constructors accept two parameters
**type**: specify the type of event
**options**: is an object with two optional properties (bubbles, cancelable - and they are false by default)
**bubbles**: if set to `true` the parent container is been fired else false
**cancelable**: if set to `true` the default behavior of the element can be prevented using `preventDefault()`. e.g (if anchor `a` is connected with an event constructor, setting the property object of `cancelable: true` allows `preventDefault()` to be effective in `a`)
The code below fires without having to use the regular events.

`e.isTrusted` returns `true` if user perform the action using mouse click or keyboard event, but if generated by Event Constructors it is `false`

## MouseEvent Properties (Application in Event Constructors)

### client

This is the feasible region around the webpage (plain white default webpage), excluding the window, navigation bar
Note: If the webpage is shrink or resized the clientX or clientY views automatically adapt to the webpage feasible region.

### screen

This is the provide measurement from the point a mouse is click, starting from the edge of the device screen (It is the entire viewport of your device)

### offset

Provide measurement of "container|single element" from border of the element to the position is was clicked

### page

Similar with client as it provide measurement of the webpage position clicked, but this time it does not base on the feasible region (i.e if the webpage is scrollable it measures through it)
**X** represent the horizontal position of the mouse pointer.
**Y** represent the vertical axis of the the mouse pointer.
`    const btn = document.querySelector(".btn");
      btn.addEventListener("click", (e) => {
        console.log(`${e.screenX}, ${e.screenY}`);
      });
      let myEvent = new MouseEvent("click", {
        bubble : true,
        cancelable: true,
        screenX: undefined,
        screenY: undefined
        clientX: undefined,
        clientY: undefined,
        offsetX: undefined,
        offsetY: undefined,
        pageX: undefined, 
        pageY: undefined
      });
      btn.dispatchEvent(myEvent);
`

## KeyboardEvent Properties (Application in Event Constructors)

`    const input = document.querySelector(".input");
      input.addEventListener("keydown", (e) => {
        console.log(`${e.key}, ${e.code}`);
      });
      let myEvent = new KeyboardEvent("keydown", {
        bubble : true,
        cancelable: true
        key:enter,
        code:enter,
      });
      input.dispatchEvent(myEvent);
`

## Event

`  
  const input = document.querySelector(".input");
      input.addEventListener("click", (e) => {
        console.log(`Dispatched`);
});
let myEvent = new Event("click", {
bubble : true,
cancelable: true

      });
      input.dispatchEvent(myEvent);

`

**_Note: MouseEvent, KeyboardEvent and Event can be used interchangeably (why because JavaScript allows for flexibility as long as the event type matches the addEventListener event)_**

## Callback Function

**The condition below is used to check if callback is actually a callback function**

`if(callback && typeof callback === "function")`
## Custom Event
Apart from having the chance to create your own event using custom event. Custom event also allows you to send various information across the webpage with the event `detail`.

`btn.addEventListener("click", () => {
        let myEvent = new CustomEvent("textSubmitted", {
          detail: {
            message: input.value,
            text: " !Winner"
          },
        });
        btn.addEventListener("textSubmitted", (e) => {
          para.textContent = e.detail.message;
          input.value = "";
          input.focus();
        });
        btn.addEventListener("textSubmitted", (e)=>{
          code.textContent = e.detail.text
        })
        btn.dispatchEvent(myEvent);
      });`

### createTextNode
It's basically for interactive appending of text to HTML elements. 

**HTML**
`<p> Hi </p>

**script**
 const para = document.querySelector("p")
 const addText = document.createTextNode('Prince')
 
 para.appendChild(addText)
`

### parentNode
As the name imply it is just a parent container.

` .replaceStyle{
        color: red;
        background:lightpink;
        font-weight:700;
      }`

`  <div class="father">Father            <div class="child">child</div></div>

From the description, `child
has a parentNode of `father`

`const child = document.querySelector(".child")

child.parentNode.classList.toggle("replaceStyle")`

What the code does is replace the `class` of the child parent and apply the class `replaceStyle` to it.

*Interesting thing is: if there is any styles made already in case with that class name, it then take the style.*
