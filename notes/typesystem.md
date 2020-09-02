---
tags: [c, java, javascript, python]
title: typesystem
created: '2019-07-30T06:19:49.256Z'
modified: '2020-08-26T08:21:43.087Z'
---

# typesystem

>

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

Language       | Static? | Implicit Conversions? | Rules Enforced? | Memory-Safe?
--             |--       |--                     |--               |--           
[[c]]          | Strong  | Depends               | Weak            | Weak        
[[java]]       | Strong  | Depends               | Strong          | Strong      
haskell        | Strong  | Strong                | Strong          | Strong      
[[python]]     | Weak    | Depends               | Strong          | Strong      
[[javascript]] | Weak    | Weak                  | Weak            | Strong      

## see also
- [[c]]
- [softwareengineering.stackexchange.com/questions/333643/what-is-a-type-system](https://softwareengineering.stackexchange.com/questions/333643/what-is-a-type-system)
- [Strong and weak typing](https://www.destroyallsoftware.com/compendium/strong-and-weak-typing)
