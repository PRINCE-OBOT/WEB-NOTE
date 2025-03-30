

The `font-display` property in CSS controls how text is displayed while web fonts load, balancing speed and aesthetics. There are five values:

- **auto**: Browser decides thebehavior. (*Different browsers handle this scenario differently. By default, Chromium-based and Firefox browsers block text rendering for up to 3 seconds if the associated web font has not loaded. Safari blocks text rendering indefinitely).

- **block**: Text stays invisible for up to 2–3 seconds, then shows fallback font; once the web font loads, it swaps in, possibly causing layout shifts.

- **swap**: Shows fallback text immediately (0ms block); swaps in the web font when it arrives, but can cause a noticeable shift.

- **fallback**: Short invisible period (100ms), then fallback font for 3 seconds before giving up; smaller chance of shift.

- **optional**: Similar to fallback, but if the font arrives late, it may never load to avoid shifts.

**Recommended strategies:**

*Also keep in mind that these two approaches can be combined: for example, 


>**use font-display: swap** for branding and other visually distinctive page elements. Use 
>
>**font-display: optional** for fonts used in body text.

