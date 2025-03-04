Animation event has three life cycle 

1. animationstart : tells when the animation start

2. animation iteration : tells the animation is in process.

3. animationend : tells the animation ended.

Animation is a CSS styling property, which by adding JavaScript animation events makes it more interactive.

**Meaning** You could write a code with JavaScript to perform an action when an animation in CSS starts, iterates or end.

```
CSS
@keyframes move{
100%{
transform: translate(50px, 90px);
      }
    }

button{
animation: move 1s 4 alternate;
    }

HTML
  <button>Submit</button>

<script>

const btn = document.querySelector('button')

btn.addEventListener('animationend', ()=>{
  btn.textContent = 'Ended'
})
```