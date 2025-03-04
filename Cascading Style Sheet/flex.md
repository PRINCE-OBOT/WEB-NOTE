In CSS Flexbox, the `flex` property is a shorthand for setting the `flex-grow`, `flex-shrink`, and `flex-basis` properties in a single declaration. This shorthand simplifies the process of defining how flex items should grow, shrink, and what their base size should be.

Here are some commonly used shorthand values for the `flex` property:

1. **`flex: initial`**
    
    - **Equivalent to**: `flex: 0 1 auto`
    - **Behavior**: The flex item does not grow but can shrink if necessary. Its size is determined by its content, but it will shrink to fit into the container if there's not enough space.
2. **`flex: auto`**
    
    - **Equivalent to**: `flex: 1 1 auto`
    - **Behavior**: The flex item can grow and shrink as needed, taking up available space in the container. Its size is based on its content but adjusts to the container's space.
3. **`flex: none`**
    
    - **Equivalent to**: `flex: 0 0 auto`
    - **Behavior**: The flex item is inflexible; it neither grows nor shrinks. Its size is strictly defined by its content.
4. **`flex: <number>`**
    
    - **Equivalent to**: `flex: <number> 1 0`
    - **Behavior**: The flex item will grow relative to other flex items based on the provided number, but it will not shrink. For example, `flex: 2` means the item will take twice as much space as an item with `flex: 1`.

**Examples:**

```css
/* Item will not grow but can shrink; size based on content */
.item-initial {
  flex: initial; /* Equivalent to flex: 0 1 auto */
}

/* Item will grow and shrink as needed; size based on content */
.item-auto {
  flex: auto; /* Equivalent to flex: 1 1 auto */
}

/* Item is inflexible; size based on content */
.item-none {
  flex: none; /* Equivalent to flex: 0 0 auto */
}

/* Item will grow twice as much as items with flex: 1 */
.item-grow {
  flex: 2; /* Equivalent to flex: 2 1 0 */
