### Path L (M70 10 L20 20 L30 30 Z)
**--- It has 2 value**

**M10** : 70 unit away from the **x - axis** 
**M10** :  10 unit away from the **y - axis** 

**L20** : The first L20 means - draw a line of 20 units long away from the *x - axis*.

**20**: The first 20 means - The endpoint of the line drawn will be 20 unit away from the *y - axis*

------After that --
The next  **L**  does not actually draw a line, it specify how far the line will be away from the *x - axis* 

**L30** : Set 30 unit away from the *x - axis* 

**30** : Create 30 unit away from the *y - axis*, creating the point of intersection for the last endpoint to join to.

### Path Q (M2 2 Q8,2 8,8)
**--- It has 2 value**

The **Q8,2**
The first **Q8**  set the curve for the x-axis. Pushes the curve further away from the line by 8 unit.

The **Q2** set the curve for the y - axis. Pushes the curve further into the line by 2 unit.

The **8,8** specify how long the line length will be, which is *8*.

And the second 8 specify how further away it is from the y - axis.

### Path C (M2,2 C2,8 0,9 8,2)

**--- It has 3 value**
**The cubic bezier curve***

#### C2,8 - This provide a means for the slope to pass through.

**C2** : means 2 unit away from the x-axis. 

**8** : means 8 unit away from the y-axis.


#### 0,9 - This adjust the point of slope.

**0** : Means move the point of slope 0 unit away from the x-axis.

**9** : Means move the point of slope 9 unit away from the y-axis.

#### 8,2 - This is what actually draws the line.

**8** : Draw a line of 8 unit long.

**2** : move the endpoint of the line drawn 2 unit away from the y-axis.

### path A ("M2,5 A 5 20 0 0 1 8 8") 

**A** property means **Elliptical Arc** 

**5 (rx)** : It determine how flatten the arc will be horizontally.

**20 (ry)** : It pulls or pushes the arc vertically.

**0 (x - axis - rotation)** : Pushes or pull the slope of the arc horizontally.

**0 (large - arc - flag)** : The value can either be **1** or **0**. 
1 means *big arc*, 0 means *small arc*.

**1 (sweep - flag)** : It indicate the direction of the arc. The value can either be **1** or **0**. 
1 means *counter - clockwise*, 0 means *clockwise*.

**8,8** : This is the actual line draw, where the first parameter 8 draw a line of 8 unit long and the second parameter 8 determine close the endpoint of the line drawn is away from the y-axis.

###  path T ()"M2,2 Q2,7 5,5 T8,8")

The **T** command use to create a smooth curve, also known as **Smooth Quadratic Curve**.

It has a single points, this is to say that the new generate curve by the *T* command simulate the behaviour of the previous curve.

**T 8,8** :  it provide a point for the previous curve endpoint to intercept it.