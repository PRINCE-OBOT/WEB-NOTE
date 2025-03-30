

### Calculating CSS Specificity Value

Why is that our first attempt at changing the color and font-weight failed? As we learned, it was because simply using the class name by itself had a _lower specificity value_ and was trumped by the other selector which targeted the unordered list with the ID value. The important words in that sentence were **class** and **ID**. CSS applies vastly different specificity weights to classes and IDs. In fact, an ID has _infinitely_ more specificity value! That is, no amount of classes alone can outweigh an ID.

Let’s take a look at how the numbers are actually calculated:

![[Pasted image 20250330090849.jpg]]


- If the element has inline styling, that automatically1 wins (1,0,0,0 points)

- For each ID value, apply 0,1,0,0 points

- For each class value (or pseudo-class or attribute selector), apply 0,0,1,0 points

- For each element reference, apply 0,0,0,1 point


You can generally read the values as if they were just a number, like 1,0,0,0 is “1000”, and so clearly wins over a specificity of 0,1,0,0 or “100”. The commas are there to remind us that this isn’t really a “base 10” system, in that you could technically have a specificity value of like 0,1,13,4 – and that “13” doesn’t spill over like a base 10 system would.


# Sample calculations

![[Pasted image 20250330090947.jpg]]


![[Pasted image 20250330091111.jpg]]


![[Pasted image 20250330091126.jpg]]


**Update:** The :not() sort-of-pseudo-class adds no specificity by itself, only what’s inside the parens is added to specificity value.


![[Pasted image 20250330091157.jpg]]



![[Pasted image 20250330091209.jpg]]


# Important notes

- The universal selector (*) has no specificity value (0,0,0,0)

- Pseudo-elements (e.g. :first-line) get 0,0,0,1 unlike their psuedo-class brethren which get 0,0,1,0

- The pseudo-class :not() adds no specificity by itself, only what’s inside it’s parentheses.

- The **!important** value appended a CSS property value is an _automatic win_. It overrides even inline styles from the markup. The only way an !important value can be overridden is with another !important rule declared later in the CSS and with equal or great specificity value otherwise. You could think of it as adding 1,0,0,0,0 to the specificity value.