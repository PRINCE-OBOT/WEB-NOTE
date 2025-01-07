```
transition-behavior: allow-discrete;
```
Normally `display` property will not transition when activate, setting allow-discrete as it transition behaviour makes it respect the time `delay` given to it.

` .child{
    width: 150px;
    height: 150px;
    background: blue;
    transition: opacity 0.5s, display 1s;
    transition-behavior: allow-discrete;
    
  }
  .child:active{
    display: none;
    opacity: 0.1;
  }`