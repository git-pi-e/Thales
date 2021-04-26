---
layout: default
title: Atomic CSS System
parent: Korolev
---

# Atomic CSS System
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

# Bounding Box & Positioning

## Position

| Classname  | What it does                  |
|:-----------------|:------------------------------|
| `.po-abs`   | `position: absolute`        |
| `.po-fix`   | `position: fixed`        |
| `.po-rel`   | `position: relative`        |
| `.po-stx`  | `position: sticky`  |
| `.z-0`  | `z-index: 0`  |
| `.z-1`  | `z-index: 1`  |
| `.z-4`  | `z-index: 4`  |
| `.z-5`  | `z-index: 5`  |

## Display Style

| Classname  | What it does                  |
|:-----------------|:------------------------------|
| `.display`   | `display: block !important`        |
| `.flex`   | `display: flex`        |
| `.flex-col`   | .flex + `flex-direction: column`        |
| `.f-wrap`   | .flex + `flex-wrap: wrap`        |

## Padding

| Classname  | What it does                  |
|:-----------------|:------------------------------|
| `.p-0`   | `padding: 0px`        |
| `.p-5`   | `padding: 5px`        |
| `.p-10`   | `padding: 10px`        |
| `.p-20`   | `padding: 20px`        |

## Margin

| Classname  | What it does                  |
|:-----------------|:------------------------------|
| `.m-h-auto`   | `margin: 0 auto`        |
| `.m-0`   | `margin: 0px`        |
| `.m-5`   | `margin: 5px`        |
| `.m-7`   | `margin: 7px`        |
| `.m-10`   | `margin: 10px`        |
| `.m-20`   | `margin: 20px`        |

## Border Radius

| Classname  | What it does                  |
|:-----------------|:------------------------------|
| `.rx-2`   | `border-radius: 2px`        |
| `.rx-5`   | `border-radius: 5px`        |
| `.rx-50`   | `border-radius: 50px`        |
| `.rx-ha`   | `border-radius: 50%`        |
| `.rx-max`   | `border-radius: 200px`        |

# Typography

## Alignment

| Classname  | What it does                  |
|:-----------------|:------------------------------|
| `.tx-c`   | `text-align: center` |
| `.tx-j`   | `text-align: justify` |
| `.tx-l`   | `text-align: left` |
| `.jtx-ar`   | `justify-content: space-around` |
| `.jtx-ct`   | `justify-content: center` |
| `.jtx-ev`   | `justify-content: space-evenly` |

## Weights

`.f-wtX` where X is the weight/100. <br/>

<span style="font-weight:100">
So `f-wt1` is `font-weight: 100` <br/>
</span>

<span style="font-weight:700">
To `f-wt7` is `font-weight: 700`
</span>

# Colours

## Backgrounds

### Singular

| Attribute 'bg'  | Value                  |
|:-----------------|:------------------------------|
| `222`   | `background: #222` <span class="d-inline-block p-2 v-align-middle" style="background:#222;" />|
| `000`   | `background: #000`  <span class="d-inline-block p-2 v-align-middle" style="background:#000;" />|
| `0008`   | `background: #0008` <span class="d-inline-block p-2 v-align-middle" style="background:#0008;" />|
| `nil`   | `background: #0000`  <span class="d-inline-block p-2 v-align-middle" style="background:#0000;" />|

### Gradients

| Attribute 'bg'  | Value                  |
|:-----------------|:------------------------------|
| `nil-000`   | <span class="d-inline-block p-2 v-align-middle" style="background:#0000;" />  <span class="d-inline-block p-2 v-align-middle" style="background:#000;" />   `background: linear-gradient(to bottom, #0000, #000)`|
| `000-nil`   |   <span class="d-inline-block p-2 v-align-middle" style="background:#000;" /> <span class="d-inline-block p-2 v-align-middle" style="background:#0000;" /> `background: linear-gradient(to top, #0000, #000)`|
| `e66-c26`   |   <span class="d-inline-block p-2 v-align-middle" style="background:#e66;" /> <span class="d-inline-block p-2 v-align-middle" style="background:#c26;" /> `background: linear-gradient(to top, #e66, #c26)`|
| `e6e-945`   |   <span class="d-inline-block p-2 v-align-middle" style="background:#e6e;" /> <span class="d-inline-block p-2 v-align-middle" style="background:#945;" /> `background: linear-gradient(to top, #e6e, #945)`|
| `b5e-83c`   |   <span class="d-inline-block p-2 v-align-middle" style="background:#b5e;" /> <span class="d-inline-block p-2 v-align-middle" style="background:#83c;" /> `background: linear-gradient(to top, #b5e, #83c)`|
| `66e-37f`   |   <span class="d-inline-block p-2 v-align-middle" style="background:#66e;" /> <span class="d-inline-block p-2 v-align-middle" style="background:#37f;" /> `background: linear-gradient(to top, #66e, #37f)`|
| `69e-8ae`   |   <span class="d-inline-block p-2 v-align-middle" style="background:#69e;" /> <span class="d-inline-block p-2 v-align-middle" style="background:#8ae;" /> `background: linear-gradient(to top, #69e, #8ae)`|

# Elements

## Width

| Classname  | What it does    |Defaults              |
|:-----------------|:---|:------------------------------|
| `.w-50`   | `width: 50%` ||
| `.w-66`   | `width: 66.66%` ||
| `.w-100`   | `width: 100%` ||
| `.w-gen`   | `width: calc(var(--base) - var(--offset))` | `--base:100%, --offset:0`|

## Height

| Classname  | What it does |
|:---|:---|
| `.h-a`   | `height: auto` |
| `.h-100`   | `height: 100%` |

# HTML Elements

## Wildcard / All

### Size

| Attribute 'size'  | Width, Height |
|:---|:---|
| `max`   | `400px` |

## Images

### Size

| Attribute 'size'  | Width, Height |
|:---|:---|
| `min`   | `22px` |
| `ic`   | `25px` |
| `ic-md`   | `66px` |
| `ic-lg`   | `100px` |
| `md`   | `150px` |
| `md-lg`   | `175px` |