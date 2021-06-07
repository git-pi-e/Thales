---
layout: default
title: Edu
nav_order: 4
has_children: true
---

# Starting Up

After cloning the repo. In a terminal in the repo.
You may use npm or pnpm

```bash
$ npm install pnpm
$ pnpm i
```

## Run
```bash
$ npm run dev
# for the SCSS compilers (global/atomic)
$ npm run sass:global
# build
$ npm run build
```

## Deploy
This command uses `gh-pages` to build and deploy the build folder to gh-pages folder
```bash
$ npm run deploy
```

For details on how SvelteKit is hosted to gh-pages [Read More](https://svelteland.github.io/svelte-kit-blog-demo/deply-to-github/).

Go to Point your web browser to [http://localhost:5000](http://localhost:5000)