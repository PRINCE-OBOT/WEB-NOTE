The `writing-mode` property in CSS is used to define the direction in which text and content flow. Here are its values with real-life relatable examples:

1. **horizontal-tb** (default) — Content flows horizontally, from left to right, and then top to bottom.  
    Example: Like reading a standard English book.
    
2. **vertical-rl** — Content flows vertically, from top to bottom, and lines are placed from right to left.  
    Example: Like reading traditional Japanese text, where each line goes downward, and lines start from the right side.
    
3. **vertical-lr** — Content flows vertically, from top to bottom, and lines are placed from left to right.  
    Example: Similar to vertical-rl, but lines begin from the left side.
    
4. **sideways-rl** — Text lines are horizontal, but rotated 90 degrees clockwise, and lines stack from right to left.  
    Example: Imagine tilting a printed poster 90 degrees clockwise; now you read the lines top-to-bottom along that rotation.
    
5. **sideways-lr** — Text lines are horizontal, rotated 90 degrees counter-clockwise, and lines stack from left to right.  
    Example: Imagine tilting a printed poster 90 degrees counter-clockwise and reading it along that rotation.
    

```css
.test {
  writing-mode: vertical-rl;
  border: 1px solid black;
  width: 100px;
}
```

