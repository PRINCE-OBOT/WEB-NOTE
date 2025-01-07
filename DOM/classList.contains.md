
It is used to check if the DOM element contain a specific class, if it has it returns `true` else `false`.

`const box = document.querySelector('.box');

`// Check if the element has the 'active' class
`if (box.classList.contains('active')) {
  console.log('The box is active.');
} else {
``  console.log('The box is not active.');
}`