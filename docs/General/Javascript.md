---
layout: default
title: Javascript
parent: General
nav_order: 2
---

# Nomenclature

Please use meaningful, crisp, self explainatory names. Don't worry about efficiency, we have a compiler to take care of that. For example to get  user's bank information, `getUserBankInfo` is much more appropriate than `getUserInfo`

**Consistency**: If for example we need a CRUD function, we use `create`, `get` or `update` with the name. If we need to get user info from the database, then the name of the function can be `userInfo`, `user` or `fetchUser`, but this is not the convention. We should use *`getUser`*.

**Avoid**: One letter variable names (other than in loop iterators). You are not a compiler. Let the compiler do its job. Stop optimising. `const q`, `function f` etc.

## Functions & Variables
camelCaseVerbs

```js
let camelCase = ''

const thisIsCamelCase = () => {
    //so something
}

function thisIsCamelCase2 () {
    //so something
}
```

## Classes & Functors
PascalCaseNouns

```js
//bad practice
class MakeCar = {
    //...
}
//Good practice
class Car = {
    //...
}
```

## Constants
ALL_CAPS_SNAKE

```js
const DAYS_IN_A_YEAR = 365;
```

# Algorithmic

## Nesting
Avoid nesting too much. A js nest of 2 levels is understandable, one of 3 levels is extremely sub par, one of 4 or beyond is absolute garbage rewrite the section.

```js
// bad practice
const array = [ [ ['SEDS Celestia'] ] ]
array.forEach((firstArr) =>{
    firstArr.forEach((secondArr) => {
        secondArr.forEach((element) => {
            console.log(element);
        })
    })
})

// good practice
const array = [ [ ['SEDS Celestia'] ] ]
const getValuesOfNestedArray = (element) => {
    if(Array.isArray(element)){
        return getValuesOfNestedArray(element[0])
    }
    return element
}
getValuesOfNestedArray(array)
```

## Avoid Very Large functions
One function should serve a total of 1 task. Preprocessing for that task may be included basis convenience

```js
// bad practice
const addSub = (a,b) => {
    // add
    const addition = a+b
    // sub
    const sub = a-b
    // returning as a string
    return `${addition}${sub}`
}

// good practice
// add
const add = (a,b) => {
    return a+b
}
// sub
const sub = (a,b) => {
    return a-b
}
```

## Avoid inline functions
Inline functions trigger a full component rerender even if it is not needed, that is just wasteful even if props don't change. It also increases the app footprint by about 40% (For that function).

```jsx
import React, { Component } from 'react';

class BadParent extends Component{
    render() {
        return (
            <Child
                onClick={()=> console.log('This is bad practice')}
            />
        )
    }
}

class GoodParent extends Component{
    function doWork() {
        console.log('This is Good practice')
    }
    render() {
        return (
            <Child onClick={doWork} />
        )
    }
}
```