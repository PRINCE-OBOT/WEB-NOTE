window.getComputedStyle is used to retrieve almost all CSS style properties applied to an element. It gives the computed styles, which are the final values after all CSS rules, inline styles, and browser defaults have been applied.

`<div id="myDiv" style="background-color: rgb(255, 2, 0);">Click me</div>


  `document.getElementById('myDiv').addEventListener('click', function(e) {
``    const bgColor = window.getComputedStyle(e.target).backgroundColor;
   `` console.log('Background color:', bgColor);
  });
