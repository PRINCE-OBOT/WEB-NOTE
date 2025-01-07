## img css properties

`object-fit:` it can be (contain, cover).
`object-position` it can be (top, bottom), it is used when the object-fit is set to _contain_

*The below code is use to fix and edit image using css and include opacity*
`.container{
      background: peachpuff;
      flex: 1;
      height: 100vh;
    }
    .container::before{
      background: url(./1.jpeg) no-repeat center/cover;
      //background: linear-gradient(to bottom, rgb(242, 48, 48,0.9) 10px, rgb(110, 10, 10, 0.9), rgb(3, 3, 76,0.9)) ;
      position: absolute;
      top: 0;
      bottom: 0;
      right: 0;
      left: 0;
      width: 100%;
      height: 100vh;
      content: "";
      color: rgb(39, 1, 1);
      background-color: black;
      z-index: 1;
    }`