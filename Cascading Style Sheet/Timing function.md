
By default timing function is set to `ease in` animation but but you can explicitly specify how the timing function should be.

### 1. ease :  

is it begins slowly, fast in the middle, then slow down when getting to the ending.

### 2. ease-out :

it begins fast and get slower at the ending.

### 3. ease-in: 

begin slow and get faster at the ending.

### 4. ease-in-out : 

start slowly, speed in the middle and slow again at the ending, just like `ease` but provide more smoother transition from the beginning to the middle and the end

### 5. cubic-bezier :

it's just a way of specify your own timing function. It has 4 parameters, (x1, y1, x2, y2)

*I kinda like to take this as it default value.*

cubic-bezier(0, 0, 1, 1)

![[IMG_20250228_072542.jpg]]

*Use this virtual cubic-bezier for demonstration*
https://cubic-bezier.com/#.7,-0.48,.41,1.41

**x values** ranges between 0 - 1
**y values** have not bound

#### Easy identification 

1. The further either **x1,y1** or **x2,y2** is push inward the **faster** it is. (In form of **U**)

2. The further either **x1,y1** or **x2,y2** is push outward the **slower** it is. (In form of **n**)

**Y-values (y1, y2)** control how fast or how slow it starts(y1) or end(y2).

**X-values (x1, x2)** controls when the speed changes.

The higher `y1,y2` values the faster it is and vice versa. 

```
CSS
animate-btn{
animation: mymove 2s cubic-bezier(0.68, -0.55, 0.27, 1.55) infinite 7;
    }

	
HTML
<button>Click Me</button>
```

*This is just a simple animation that tells button how it will be move around the windows.


