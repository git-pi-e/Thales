---
layout: default
title: CSS Optimisation
parent: General
nav_order: 4
---

# Speed Considerations

## Content-Visibility
Use `content-visibility` to skip the rendering of the off-screen content.
The simplest way is to just use `content-visibility:auto` and let the browser take care of invisible segments

![Web.dev](https://web-dev.imgix.net/image/admin/v6WcSx9Fq76lCD0iqFCQ.jpg?auto=format&w=845)
Image: Web.dev

> *Invisible elements can still be navigated to in the accessibility tree, to prevent this add `aria-hidden="true"` HTML attribute also*

Content-Visibility API can be used in conjunction with `contain-intrinsic-size` for maximum speed since it informs the browser before hand on what to expect, this will solve the scrollbar snapping issue with is caused when an element is rendered with height 0px.

### Comparison with other hiding methods
- `display: none`: hides the element and destroys its rendering state. This means unhiding the element is as expensive as rendering a new element with the same contents.
- `visibility: hidden`: hides the element and keeps its rendering state. This doesn't truly remove the element from the document, as it (and it's subtree) still takes up geometric space on the page and can still be clicked on. It also updates the rendering state any time it is needed even when hidden.
- `content-visibility: hidden`, on the other hand, hides the element while preserving its rendering state, so, if there are any changes that need to happen, they only happen when the element is shown again (i.e. the content-visibility: hidden property is removed)

## Will-Change
Using `will-change` indicates that the element will change in the future.
So if you try to use `will-change` along with an `animation` simultaneously, it will not give you the optimization. Therefore, it is recommended to use `will-change` on the parent element and the `animation` on the child element
```css
.my-class{
  will-change: opacity;
}
.child-class{
  transition: opacity 1s ease-in-out;
}
```

> _**Do not use elements that are not animating.** When you use will-change on an element, the browser will try to optimize it by moving the element into a new layer and handing over the transformation to the GPU. If you have nothing to transform, it will result in a waste of resources_

## Code Splitting

### By Size
```css
<!-- style.css contains only the minimal styles needed for the page rendering -->
<link rel="stylesheet" href="styles.css" media="all" />
<!-- Following stylesheets have only the styles necessary for the form factor -->
<link rel="stylesheet" href="sm.css" media="(min-width: 20em)" /><link rel="stylesheet" href="md.css" media="(min-width: 64em)" /><link rel="stylesheet" href="lg.css" media="(min-width: 90em)" /><link rel="stylesheet" href="ex.css" media="(min-width: 120em)" /><link rel="stylesheet" href="print.css" media="print" />
```
Splitting CSS files by size will reduce render blocking time since it will then load the irrelevant files but not process them. It will render only the base and the one specifically matching the size

### By Call
Always prefer `<link>` in HTML over `@import` in CSS. It is miles better for performance


# Construction Considerations

## Writing
Stop writing CSS. Write in SCSS only. Let the compiler do the work for you, this also has the added benefit of an automatically minified css with no extra work

## Structuring

### SVGs (Marked for Update)
Keep `stroke-linecap`, `stroke-linejoin` and `stroke-width` constant across any given website by setting it in root for icons. Since all icons are CURRENTLY separate files

It would be best to combine all of them into a single file and load it as an SVG font