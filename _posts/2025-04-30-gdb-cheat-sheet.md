---
layout: post
title: GDB Cheat Sheet
categories:
 -
---

# Add debug flag at compile time

```sh
cc -g 
gdb ./a.out
```

# Gdb command collections

- b file:linenr | add a break point
- l . | show code at breakpoint
- c-x a | toggle tui
- c-l | redraw/clear screen
- n | next 

