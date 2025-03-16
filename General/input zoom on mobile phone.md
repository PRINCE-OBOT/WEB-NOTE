Yes, in general:

1. **Font sizes below `1rem` (16px)** may trigger zoom-in on mobile browsers, especially in **Safari on iPhones** and some older Android browsers.
2. **Font sizes `1rem` (16px) or greater** will **not** trigger zoom-in on input focus.

However, some factors affect this behavior:

- **Browser & OS**: Newer Chrome versions on Android often **don't zoom** even if the font size is small. Safari on iPhones is more likely to zoom.

- **Viewport meta tag**: If `<meta name="viewport" content="width=device-width, initial-scale=1">` is missing or modified, zooming behavior can change.

- **User settings**: Some users manually disable auto-zoom in browser settings.

If you're building a site and want to **prevent unintended zooming**, keeping input font sizes **at least 16px (1rem)** is a good rule of thumb.