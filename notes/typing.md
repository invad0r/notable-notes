---
tags: [c, java, javascript, python]
title: typing
created: '2019-07-30T06:19:49.256Z'
modified: '2019-08-20T09:46:36.492Z'
---

# typing

#### when is type information required ?
| compiletime | runtime   |  
|--           |--         |  
| `static`    | `dynamic` |  

#### how strictly distinguished ?
| | |
|--           |--                       |
| `weak`      | implicit conversion     |
| `strong`    | no implicit conversion  |
| `type-safe` | compiler validates types during compilation |

`implicit conversion`: `string` -> `number`

### language differences

| Language       | Static? | Implicit Conversions? | Rules Enforced? | Memory-Safe? |
|--              |--       |--                     |--               |--            |
| [[c]]          | Strong  | Depends               | Weak            | Weak         |
| [[java]]       | Strong  | Depends               | Strong          | Strong       |
| haskell        | Strong  | Strong                | Strong          | Strong       |
| [[python]]     | Weak    | Depends               | Strong          | Strong       |
| [[javascript]] | Weak    | Weak                  | Weak            | Strong       |

[Strong and weak typing – Programmer's Compendium](https://www.destroyallsoftware.com/compendium/strong-and-weak-typing?share_key=6b0dd1ec18ab6102)
