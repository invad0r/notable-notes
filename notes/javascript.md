---
tags: [javascript]
title: javascript
created: '2019-08-19T12:09:44.017Z'
modified: '2023-05-23T16:49:55.443Z'
---

# javascript

> interpreted, or jit-compiled programming language with first-class functions

> has more in common with functional languages like [[lisp]] or [[scheme]] than with [[c]] or [[java]]. 
> It has arrays instead of lists and objects instead of property lists. 
> Functions are first class. It has closures. You get lambdas without having to balance all those parens.
> [crockford.com/javascript/javascript](https://crockford.com/javascript/javascript.html)

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

[[node]], [[js]], [[deno]], [[bun]]

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

## object patterns

> `private` and `privileged` members can only be made when an object is constructed. Public members can be added at any time.

```js
function Container(param) {
    // var dec = function dec(...) {...};
    // shorthand:
    function dec() {                          // private method
        if (secret > 0) {
            secret -= 1;
            return true;
        } else {
            return false;
        }
    }

    this.member = param;                      // public
    var secret = 3;                           // private
    var that = this;                          // private, convention used to make the object available to private methods

    this.service = function () {              // protected method
        return dec() ? that.member : null;    // 3 calls allowed
    };
}

Container.prototype.memberName = value;       // public

c = new Container("foo");
```

[crockford.com/javascript/private](https://crockford.com/javascript/private.html)

## implement "react hooks"

```js
function useState(initVal) {
  _val = initVal;
  const state = () => _val; // add `() =>` turns it into setter function
  const setState = newVal => {
    _val = newVal;
  }
  return [state, setState]
}

const [count, setCount] = useState(1)
console.log(count())
setCount(2)
console.log(count())
```

[react.dev/reference/react](https://react.dev/reference/react)
[Can Swyx recreate React Hooks and useState in under 30 min? - JSConf.Asia](https://www.youtube.com/watch?v=KJP1E-Y-xyo)

## closure

```js
function getAdd() {
  let foo = 1;
  return function() { // anonymous function which is the closure, "encloses" foo value
    foo = foo + 1;
    return foo;
  }
}
const add = getAdd();

/*
 * "module pattern" / "IIFE" (=immediately-invoked function expression)
 */
const add = (getAdd() {
  let foo = 1;
  return function() { // anonymous function which is the closure, "encloses" foo value
    foo = foo + 1;
    return foo;
  }
})();

// change internal state
console.log(add());
console.log(add());
// foo = 23  // can't change internal val foo !
console.log(add());
console.log(add());
```

## see also

- [[nvm]]
- [[tsc]], [[coffee]]
- [[mongo]]
- [[go]], [[rust]], [[java]]
- [developer.mozilla.org/en-US/docs/Web/JavaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript)

