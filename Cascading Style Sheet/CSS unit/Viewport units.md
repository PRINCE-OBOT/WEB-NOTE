
### What are viewport units?

- **Viewport Width** (`vw`) – A percentage of the full viewport width. `10vw` will resolve to 10% of the current viewport width, or `48px` on a phone that is `480px` wide. The difference between `%` and `vw` is most similar to the difference between `em` and `rem`. A `%` length is relative to local context (containing element) width, while a `vw` length is relative to the full width of the browser window.

- **Viewport Height** (`vh`) – A percentage of the full viewport height. `10vh` will resolve to `10%` of the current viewport height.

- **Viewport Minimum** (`vmin`) – A percentage of the viewport width or height, _whichever is smaller_. `10vmin` will resolve to `10%` of the current viewport width in portrait orientations, and `10%` of the viewport height on landscape orientations.

- **Viewport Maximum** (`vmax`) – A percentage of the viewport width or height, _whichever is larger_. `10vmax` will resolve to `10%` of the current viewport height in portrait orientations, and `10%` of the viewport width on landscape orientations. Sadly, and strangely, `vmax` units are not yet available on Internet Explorer or Edge.