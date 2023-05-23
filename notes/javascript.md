---
tags: [javascript]
title: javascript
created: '2019-08-19T12:09:44.017Z'
modified: '2023-05-19T12:50:44.148Z'
---

# javascript

> interpreted, or jit-compiled programming language with first-class functions

## runtimes

|                |           |
| ---            | ---       |
| [[node]].js    | open-source, cross-platform, JavaScript runtime built on Chrome's V8 JavaScript engine |
| [[deno]]       | secure runtime for [[javascript]] and [[typescript]] built on V8 engine, and designed to improve on Node.js |
| Rhino          | engine written in [[java]], which allows [[javascript]] to be run on jvm |
| JerryScript    | engine used on devices with limited resources, such as microcontrollers |
| SpiderMonkey   | engine used in Mozilla [[firefox]], [[js]] |
| JavaScriptCore | engine used in Apple's Safari browser |
| Chakra         | engine used in Microsoft Edge and Internet Explorer |
| Nashorn        | engine for the JVM, introduced in [[java]] 8 and deprecated on version 15 |
| QuickJS        | small and embeddable engine with a focus on performance and compliance |
| V8             | engine used in chrome and Chromium-based browsers                |
| MuJS           | lightweight interpreter that supports ES5 and a subset of ES6 |
| Jint           | .NET-based interpreter that allows you to run JavaScript code within a .NET application |

```
              ┌────────┐      ┌─────────┐    ┌───────┐
              │ Source ├──────► parser  ├────► AST   │
              └────────┘      └─────────┘    └───┬───┘
                   ┌─── ─── ─── ─── ── ─── ─── ──┘
      ┌────────────┼──────────────────────────────────────────┐
      │       ┌────▼─────────┐         ┌─────────────┐     d  │
      │       │ interpreter  │         │  bytecode   │     e  │
      │ o ┌───┤              ├─────────►             ◄───┐ o  │
      │ p │   └──────────────┘         └──────┬──────┘   │ p  │
      │ t               profiling data        │            t  │
      │ i │           ┌───  ─── ─── ─── ─── ──┘          │ i  │
      │ m     ┌───────▼──────┐         ┌─────────────┐     m  │
      │ i │   │ optimizing   │         │ optimized   │   │ i  │
      │ z └───►  compiler    ├─────────►   code      ├───┘ z  │
      │ e     └──────────────┘         └─────────────┘     e  │
      └───────────────────────────────────────────────────────┘
```

[mathiasbynens.be/notes/prototypes](https://mathiasbynens.be/notes/prototypes)


## install

[[node]], [[js]]

## datatypes

```js
//[7] data types
object

//[6] primitive types
boolean
null
undefined
number
string
symbol          // (ecma6)

// array

// slice() method returns a shallow copy of a portion of an array into a new array object selected from start to end
const items = [1,2,3,4,5];
const slice = items.splice(1,3);
console.log(items);                     // [ 1, 5 ]
console.log(slice);                     // [ 2, 3, 4 ]
```

## see also

- [[js]], [[node]], [[nvm]]
- [[tsc]], [[coffee]]
- [[mongo]]
- [[go]], [[rust]], [[java]]
- [developer.mozilla.org/en-US/docs/Web/JavaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
