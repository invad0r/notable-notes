---
tags: [javascript]
title: coffeescript
created: '2023-05-13T11:57:06.368Z'
modified: '2023-05-24T08:41:17.237Z'
---

# coffeescript

> little language that compiles into [[javascript]]

## install

[[coffee]]

## language

```js
class Animal
  constructor: (@name, @species) ->

  speak: ->
    console.log "Hi, I'm #{@name} the #{@species}!"

dog = new Animal("Buddy", "dog")
dog.speak()
```

## see also

- [[typescript]]
- [coffeescript.org](https://coffeescript.org)
