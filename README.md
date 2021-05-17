# My resume in plain CSS and HTML

## [View here](https://aarontabuchi.github.io/resume/)

## Problems/Learnings

### Browser discrepancies: opacity, color, layout

![screenshot](./screenshot.png)
`Screenshot - Browsers from left to right: Chrome 90.0, Safari 14.1, Firefox 88.0`

- For the glassmorphism effect, each section has a white background with an opacity between 0.25 and 0.8. Chrome, Safari, and Firefox all seem to calculate and display the opacity differently, Chrome having the least, and Firefox having the most opacity. I'll have to investigate these differences.
  - Upon further investigation, [Firefox does not support CSS-backdrop-filter](https://caniuse.com/css-backdrop-filter)
  - Also, I'm not sure if this is a bug or working as intended, but Chrome removes the backdrop-filter when printing the page :(

- Safari and Chrome seem to display colors the same, while Firefox displays them slightly brighter/more vibrant. From a quick search it looks like browsers might have different color profiles, but I'd need to research this more.

- Safari and Chrome are displaying the same layout and sizing for everything. Firefox seems to be making the line-height slightly more than the other two and also collapsing the bottom of my main container. I should do a CSS reset and test further to try to understand the differences.

- Edge and Chrome are indistinguishable, presumably because they are both running Chromium

### Font-sizing
#### Problem
My project had fractional font-sizes from doing 0.9rem with a root font-size of 16px, which calculates to 14.4px. The browsers would display different sizes with franctional/decimal sizes, so I changed all my font-sizes to calculate to whole pixel sizes.

#### Learning
Make sure that rem values calculate to whole pixel values if you want your design to be pixel perfect, otherwise fractional values are okay. Also, I could have used pixel instead of rem from the start, because I don't need my resume to be responsive to font-size.
