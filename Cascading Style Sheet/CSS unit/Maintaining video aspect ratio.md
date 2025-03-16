

Here’s how it works:

1. **Aspect Ratio Calculation**  
    The standard aspect ratio for most videos is **16:9**, meaning for every 16 units of width, there should be 9 units of height. This is applied using:
    
    ```css
    video{
      width : 100vw;
      height: calc(100vw * (9/16));
    }
    ```
    
    - `100vw` makes the video take the full width of the viewport.
    - `calc(100vw * (9/16))` calculates the height dynamically based on that width.
    - This ensures the video scales proportionally when resizing the screen.

2. **Constraining Maximum Dimensions**  
    If the video shouldn't be too large, a max-width is added:
    
    ```css
    max-width: 30em;
    max-height: calc(30em * (9/16));
    ```
    
    - This prevents the video from exceeding `30em` in width.
    - The `max-height` is also adjusted using the same `9/16` ratio, keeping it consistent.

3. **Scalability with Viewport Units**  
 
 Instead of fixed pixel sizes, `vmin` or `vw` can be used for text and elements inside the video container, ensuring everything scales uniformly when the screen resizes.
    

*This method guarantees that the video maintains its original proportions, preventing distortion while allowing it to adjust fluidly to different screen sizes.


# Why is 9 divided by 16?

The **9/16** in the formula represents the aspect ratio of a standard widescreen video.

Aspect ratio is defined as **width:height**.  

For a **16:9** video, the width is 16 units, and the height is 9 units.  
To find the height relative to the width, you divide the height by the width:

Aspect Ratio=HeightWidth=916\text{Aspect Ratio} = \frac{\text{Height}}{\text{Width}} = \frac{9}{16}

This fraction ensures the height always remains proportionate to the width.

### Finding `height` in `vh`

If you want to calculate the height in viewport height (`vh`) instead of `vw`, you would invert the formula:

width=height×169\text{width} = \text{height} \times \frac{16}{9}

So, if you know the height in `vh`, you can get the width as:

```css
.full-height {
  height: 100vh;
  width: calc(100vh * (16/9));
}
```

This approach ensures that the video scales consistently whether you define it based on `vw` or `vh`.