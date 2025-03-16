### [Hybrid](https://mattbrictson.com/blog/css-normalize-and-reset#hybrid)

**Is a combination of a normalize and reset stylesheet.

The idea is that you want the bug fixes and remediation of browser oddities that are typically part of a normalize stylesheet, plus the zero-margin clean slate that is the job of a reset stylesheet. Together these provide the blank canvas developers want, and without any browser surprises.

Unlike a pure reset, these hybrid-reset stylesheets will often add some opinionated defaults of their own, like setting `box-sizing: border-box` or adding `img { max-width: 100% }` to make images more responsive.