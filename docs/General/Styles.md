---
layout: default
title: Styles & Design
parent: General
nav_order: 3
---

# Typography

## Fonts
Any fonts less than 12px must STRICTLY be <span style="font:600 11px Times">Serif</span> only.

# Images
## Size
- The maximum size of any image for the given component must be 10% more than its size in pixels on a standard 1080p display. So say if it is supposed to be 600x400, make it not more than 660x440
- All images (Exception: External Images & SVGs) must have `srcset` attribute and must have multiple images to display the correct size on the correct display. A mobile does not need to load a 4K image
- All images must have strictly defined height and width, either inline or in CSS

## Fallbacks
All images must have `onerror`
```html
<img src="" srcset="" alt="About the image" onerror="this.src = 'someOtherImage'" />
```
as a fallback to display another image of same dimensions in case this doesn't load & an alt attribute for the visually impaired