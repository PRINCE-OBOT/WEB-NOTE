It is use to fire event without user performing the event.

**Note** Always define your categories of event properly when creating your constructor.

## Event constructors accept two parameters

**type**: specify the type of event

**options**: is an object with two optional properties (bubbles, cancelable - and they are false by default

`let myEvent = new Event(type, option)`

### bubbles

It is `false` by default.

if set to `true` it **stop propagation**

**Why not use propagation instead?**
Setting bubbles to `true or false` control whether the `.con` should also listen to the event from the `.child` when it is **despatched**.


```
HTML
<div class="con">Con
 <div class="child">Child</div>
</div>

SCRIPT
const con = document.querySelector('.con')
const child = document.querySelector('.child')

let myEvent = new MouseEvent('click')

con.addEventListener('click' ()=> alert('con'))

child.addEventListener('click' ()=> alert('con'))

child.dispatchEvent(myEvent)
```

### cancelable

it is `false` by default.

**Note** Before you define the event for the constructor (like, Mouse event, Event, KeyboardEvent ...), you should consider how the element behave naturally.

*For example,

An `<a>` element is been clicked using the MouseEvent, so when defining the constructor you should ensure you imply same.

```
let myEvent = new MouseEvent('click', {})
```
___

`{cancelable : true}`
Means 
*The element behaviour can be prevented with* **preventeDefault()

`{cancelable : false}`
Means
*The element behaviour cannot be prevented with* **preventDefault()

**Note** the **cancellable** only controls the **preventeDefault** when it is dispatched, meaning after been despatched, **preventDefault()** now has full control.

```
a.addEventListener('click', (e) => {
        e.preventDefault();
    });

a.dispatchEvent(myEvent)
```

