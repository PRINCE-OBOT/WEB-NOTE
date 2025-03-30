

### **What is `flex`?**

`flex` is a shorthand CSS property that controls how an item inside a flex container will grow, shrink, and what its default starting size (basis) should be.

In shorthand form:  
`flex: flex-grow flex-shrink flex-basis`

- **`flex-grow`**: If there's extra space on the bench, how much will you stretch?
    
- **`flex-shrink`**: If the bench gets smaller (not enough space), how much will you squeeze yourself in?
    
- **`flex-basis`**: What size do you start with before growing or shrinking?
    

---

### **Breaking Down Real Examples:**

1. **flex: auto**  
    This is like saying:  
    _"I'll sit with my default size, but if there's extra room, I'll stretch; if there's less space, I'll squeeze."_  
    CSS means: `flex: 1 1 auto`
    
2. **flex: none**  
    _"I will sit in my exact size, and I won’t stretch or shrink."_  
    CSS means: `flex: 0 0 auto`
    
3. **flex: initial**  
    _"I won’t grow, but I’ll shrink if I need to. I sit in my normal size otherwise."_  
    CSS means: `flex: 0 1 auto`
    
4. **flex: 2**  
    _"I will start with no defined size (flex-basis: 0%), and I will stretch two times more than others if there’s free space. But I can shrink as well."_  
    CSS means: `flex: 2 1 0%`
    
