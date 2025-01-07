 @font-face {
  font-family: Outfit;
  src: url('fonts/Outfit-Regular.ttf');
  font-weight: 500;
}

@font-face {
  font-family: Outfit;
  src: url('fonts/Outfit-Bold.ttf');
   font-weight: 400;
}

.title {
font-family: Outfit;
font-weight:400;
  font-size: 12px;
  color: blue;
}

**@font-face** is used when you want to use your own custom font family.

1. Start by defining the name of the font-family `Outfit`

2. And then the path in your device `fonts/Outfit-Regular.ttf`

3. Then the font-weight 
   The font weight has two main purpose,
1. To map the actual element to the specific font-family 
2. And to manage the weight(thickness or lightness) of the text.

4. Lastly we have the `font stye`