##,feBlend : it is used for blending images or color on one another 

`<svg width="200" height="200" xmlns="http://www.w3.org/2000/svg">
  `<defs>
    `<filter id="blendFilter">
      `<feFlood flood-color="red" result="redRect" width="100%" height="100%" />
     `<feFlood flood-color="blue" result="blueCircle" />
      `<feBlend in="redRect" in2="blueCircle" mode="multiply" />
    `</filter>
  `</defs>

  `<rect x="0" y="0" width="200" height="200" filter="url(#blendFilter)" />
`</svg> 