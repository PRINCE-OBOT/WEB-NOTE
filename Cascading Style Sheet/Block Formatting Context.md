
**Block Formatting Context** is an invisible protective container that prevents outside floats and margin collapsing from disturbing the inside layout.


>"BFC is like placing an element into a more secure, invisible box that makes sure outside floating elements or collapsing margins do not disturb, alter, or collapse the container or its content. It makes the container respect its boundaries."


*Example*


```html

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Margin Collapse Clear Demo Side by Side</title>
  <style>

   ​.outer{
     width: 200px;
     height: 200px;
     background: #637;
   }
   .child{
     margin: 30px 0 0 0;
   }
   
  </style>
</head>
<body>
 
    <div class="outer">
      <div class="child">
       BFC
      </div>
    </div>
//The div.outer will move away from the top by 30px even though the margin-top was applied on the child.

//To stop this apply display:flex, overflow:hidden...
</body>
</html>

```