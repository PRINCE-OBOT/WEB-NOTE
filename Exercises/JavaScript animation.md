let history = null  
function start(){
if(history == null){
history = setInterval(animates, 1)
 }
}

function stop(){
if(history !== null){
clearInterval(history)
history = null
  }
}


function animates(){
 let cx = circle.getAttribute("cx")
 let newCX = 1 + parseInt(cx)
 if(newCX > 100){
   newCX = 10
 }
 circle.setAttribute("cx", `${newCX}`)
}