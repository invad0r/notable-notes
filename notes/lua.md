---
tags: [lua]
title: lua
created: '2020-09-02T12:55:03.179Z'
modified: '2023-05-13T15:07:08.937Z'
---

# lua

> lightweight, high-level, multi-paradigm programming language designed primarily for embedded use in applications
> was designed, to be integrated with software written in `c` and other conventional languages

## install

```sh
apt install build-essential libreadline-dev

curl -R -O http://www.lua.org/ftp/lua-${VERSION}.tar.gz
tar -zxf lua-${VERSION}.tar.gz && cd lua-${VERSION}
make linux test && make install
```

## usage

```sh
lua               # standalone interpreter and interactive shell

lua hello.lua     # run script
```

## language

```lua
-- Create a prototype object
local person = {
  name = "John",
  age = 30,
  sayHello = function(self)
    print("Hello, my name is " .. self.name)
  end
}

-- Create a new object that inherits from the prototype
local student = {
  studentID = "12345"
}
setmetatable(student, {__index = person})

-- Use the inherited properties and methods
print(student.name)
print(student.age)
student:sayHello()
```

## see also

- [[nvchad]]
- [[luac]]
- [[luarocks]]
- [[nginx]]
- [[javascript]]
- [[tcl]]
- [[awk]]
- [[groovy]]
- [lua.org/pil/contents.html](https://www.lua.org/pil/contents.html)
- [Learn Lua in 15 Minutes (2013) | Hacker News](https://news.ycombinator.com/item?id=23694667)

