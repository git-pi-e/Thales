---
layout: default
title: Security
parent: General
nav_order: 1
---

# Security
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

# External Files

- All external files for JS must have an integrity check and a cross origin anonymous. This will prevent data compromised on the fly from being used.

# Data Protection
Since all repositories are open source, data must be protected in case anything is sensitive to prevent scraping.

## Images
- Images are to be fetched, converted to Image Objects and pushed to Canvas to paint it.

## Text
- Any text/urls that need to be obfuscated are to be converted to base64 and used by converting back on run. Ex. `fetch(atob(URL64))`. Custom functions may be created for this purpose

# Javascript
- DON'T use `eval`, if it is absolutely unavoidable even with `new Function`, convert it to `eval2 = eval` to scope it.
- Add a return value to all functions. If they don't serve the purpose of calculation, add a `return 0` at the end to ensure clean termination.