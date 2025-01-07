This refer to the initial style of an element before it is generated in the render tree.

**Note** to make `starting-style` effective you need to include each style you want to display before the render tree in the transition property.

.child{
    width: 150px;
    height: 150px;
    background: blue;
    transform: translateY(30px);
    transition: opacity 0.5s, display 1s, background 4.7s, transform 4s;
    transition-behavior: allow-discrete;
   /* transition: opacity 1.9s, background 0.5s ease-in-out 4s;*/
    @starting-style {
    opacity: 0.1; /* Start as invisible */
    background: pink;
    transform: translateY(10px); /* Start below */
  }