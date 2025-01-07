

` function facibonic(num){
   if(num <= 0) return [0]
   if(num === 1) return [0, 1]
   
   const sequence = [0, 1]
   
  for(i=2; i<=num; i++){
  sequence.push(sequence[i-2] + sequence[i-1])
  }
  return sequence
 }
 console.log(facibonic(6))  `