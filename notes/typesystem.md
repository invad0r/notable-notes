---
tags: [c, java, javascript, python]
title: typesystem
created: '2019-07-30T06:19:49.256Z'
modified: '2020-09-02T12:45:16.259Z'
---

# typesystem

> type system is a mechanism for defining, detecting, and preventing illegal program states. It works by defining and applying constraints. The constraint definitions are types, and, the constraint applications are usages of types, e.g. in variable declaration

#### when is type information required ?
- at compiletime - `static`
- at runtime - `dynamic`

#### how strictly distinguished ?
- implicit conversion (`string` -> `number`) - `weak`     
- no implicit conversion - `strong`   
- compiler validates types during compilation - `type-safe`



### language differences

Language       | `static` | implicit conversion | rules enforced  | memory-safe
--             |--       |--                     |--               |--           
[[c]]          | Strong  | Depends               | Weak            | Weak        
[[java]]       | Strong  | Depends               | Strong          | Strong      
[[haskell ]]   | Strong  | Strong                | Strong          | Strong      
[[python]]     | Weak    | Depends               | Strong          | Strong      
[[javascript]] | Weak    | Weak                  | Weak            | Strong      

## see also
- [softwareengineering.stackexchange.com/../what-is-a-type-system](https://softwareengineering.stackexchange.com/questions/333643/what-is-a-type-system)
- [Strong and weak typing](https://www.destroyallsoftware.com/compendium/strong-and-weak-typing)
