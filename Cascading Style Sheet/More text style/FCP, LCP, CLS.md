
FCP (First Contentful Paint) and LCP (Largest Contentful Paint) are key performance metrics used to measure how quickly a webpage loads and becomes visually useful to users.

### **First Contentful Paint (FCP)**

FCP measures the time from when the page starts loading to when the first piece of content (text, image, or non-white canvas) is displayed on the screen. It tells you how fast the page starts showing something useful.

**Example:**  
Imagine you're opening a webpage. If you see a blank screen for the first 2 seconds, then suddenly the page's logo or some text appears, that moment is the FCP.

### **Largest Contentful Paint (LCP)**

LCP measures the time it takes for the largest visible element on the screen (usually a big image, video, or block of text) to fully render. It helps measure how quickly the main content becomes available.


# Cumulative Layout Shift (CLS)

In simple terms, CLS measures how much visible content on a webpage moves around unexpectedly while the page is loading.


**Example:**  
You open an article, and first, you see a small logo (FCP). But the main content—like a big featured image or headline—takes longer to load. When that large element fully appears, that’s LCP.

### **How Web Fonts Affect These Metrics**

If a web font is delayed in loading, the text won't be displayed immediately, causing a delay in FCP. If the largest text block on the page depends on the font, it can also delay LCP. This is why using system fonts or optimizing font loading (like using `font-display: swap;`) can help improve these metrics.

Let me know if you need further clarification!