---
layout: default
title: Korolev
nav_order: 3
has_children: true
---

# Working with Korolev
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

### Structure

```
|-- root
|   |-- docs (Public)
|   |   |-- assets - Images and icons
|   |   |-- build - Compiled JS & CSS
|   |   |-- css - Stores Atomic & Global SCSS
|   |   `-- Galileo - /Galileo
|   `-- src
|       |-- data - All JSON static data
|       |-- pages - All Pages/Tabs
|       |-- shared - Components shared in multiple pages
|       `-- micro, nano - Components to large to be in pages
|-- package.json
|-- rollup.config
`-- lic, readme
```

### Starting Up

After cloning the repo. In a terminal in the repo.
You may use npm or pnpm

```bash
$ npm install
```

### Run
```bash
$ npm run dev
# for the SCSS compilers (global/atomic)
$ npm run sass:global
# build
$ npm run build
```

Go to Point your web browser to [http://localhost:5000](http://localhost:5000)