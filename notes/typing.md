---
tags: [lang]
title: typing
created: '2019-07-30T06:19:49.256Z'
modified: '2019-07-30T06:58:52.928Z'
---

# typing

#### when is type information required ?
| compiletime | runtime   |
|--           |--         |
| `static`    | `dynamic` |

#### how strictly distinguished ?
`weak` => implicit conversion
`strong`=> no implicit conversion e.g. string -> number
`type-safe` => compiler validates types during compilation


### language differences

| Language   | Static? | Implicit Conversions? | Rules Enforced? | Memory-Safe? |
|--          |--       |--                     |--               |--            |
| C          | Strong  | Depends               | Weak            | Weak         |
| Java       | Strong  | Depends               | Strong          | Strong       |
| Haskell    | Strong  | Strong                | Strong          | Strong       |
| Python     | Weak    | Depends               | Strong          | Strong       |
| JavaScript | Weak    | Weak                  | Weak            | Strong       |

[Strong and weak typing – Programmer's Compendium](https://www.destroyallsoftware.com/compendium/strong-and-weak-typing?share_key=6b0dd1ec18ab6102)
