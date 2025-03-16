Line height increases proportionally to the font size **only when it is set using a unitless value** (like `1.5`). If you set it using absolute units (like `px`, `em`, or `%`), then it follows a different rule. Let me break it down:

1. **Unitless Line Height (Recommended Approach)**
    
    - Example: `line-height: 1.5;`
    - This means the line height is **1.5 times** the font size.
    - If the font size is `16px`, the computed line height will be `16px × 1.5 = 24px`.
    - If the font size increases to `20px`, the computed line height will be `20px × 1.5 = 30px`.
    - **Result:** The line height scales automatically with the font size.
2. **Line Height with Absolute Units**
    
    - Example: `line-height: 24px;`
    - This means the line height stays fixed at `24px`, no matter what the font size is.
    - If the font size increases, the line height remains the same, which can sometimes cause text to appear too cramped or too spaced out.
3. **Percentage Line Height**
    
    - Example: `line-height: 150%;`
    - This works similarly to unitless values, but the percentage is relative to the **element's font size**, not the parent's.
    - `150%` means `1.5 × font-size`, so it behaves similarly to `1.5` in most cases.
