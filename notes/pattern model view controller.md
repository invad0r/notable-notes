---
tags: [Notebooks, pattern]
title: pattern model view controller
created: '2019-07-30T06:19:49.177Z'
modified: '2019-08-18T14:56:22.526Z'
---

# pattern model view controller

from stackskills byte sihe chungs: java mvc

`architectural pattern` for user-interfaces

`Model`: stores data underlying the user interface
`View`: visual representation
`controller`: interacts with user and modifies the model and the view

@startuml
:User: as user
(view)<--(user):sees\nthe
(controller)<--(user):interacts\nwith
(view)<..(controller):updates
(model)<..(controller):updates
(view)<..(model):updates
@enduml

```mermaid 
graph BT
  c((controller)) -- foo --> ((vview__))
  c((controller)) -- foo --> ((mmodel))
``` 

```mermaid 
graph BT
  c((controller))-.-foo-.-> v((view__))
  c((controller))-.-foo-.-> m((model))
```


What is the basic point of th e mvc-pattern ?
* seperation of data from its visual representation
* seperation of data from its manipulation
* allowing different simultanesous represenations of the same data


[Use case Diagram syntax and features](http://plantuml.com/use-case-diagram)
