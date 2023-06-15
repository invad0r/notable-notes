---
tags: [markdown, Notebooks]
title: mermaid
created: '2019-08-01T10:42:32.003Z'
modified: '2023-05-24T08:39:20.674Z'
---

# mermaid

[rich-iannone.github.io/DiagrammeR/mermaid](https://rich-iannone.github.io/DiagrammeR/mermaid.html)

## graph
- `LR` left to right
- `RL` right to left
- `TB` top to bottom
- `BT` bottom to top
- `TD` top down (same as `TB`)


- `-->` arrow connection
- `---` line connection
- `==>` `==` thick line

```mermaid
graph LR
   A -- text --> B
   B -- foo --> C
```

```mermaid
graph LR
  A(node text)
```

```mermaid
graph LR
  A((node text))
```

```mermaid
graph LR
  A{node text}
```

```mermaid
graph LR
  A>node text]
```



## Flowchart
```mermaid
graph TD;
    A-->B;
    A-->C;
    B-->D;
    C-->D;
```

## Sequence diagram

```mermaid
sequenceDiagram
    participant Alice
    participant Bob
    Alice->>John: Hello John, how are you?
    loop Healthcheck
        John->>John: Fight against hypochondria
    end
    Note right of John: Rational thoughts <br/>prevail!
    John-->>Alice: Great!
    John->>Bob: How about you?
    Bob-->>John: Jolly good!
```

## git graph

```mermaid
gitGraph:
options
{
    "nodeSpacing": 150,
    "nodeRadius": 10
}
end
commit
branch newbranch
checkout newbranch
commit
commit
checkout master
commit
commit
merge newbranch
```


## see also

- [[markdown]]



