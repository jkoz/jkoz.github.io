---
layout: post
title: GDB Cheat Sheet
categories:
 -
---

# Mode line Emacs movement keys

c-b: move backward 1 character
c-f: move forward 1 character
c-d: delete a character under cursor
c-w: delete 1 word from current cursor towards front of the line

# Add debug flag at compile time

```sh
cc -g 
gdb ./a.out
```

# Gdb command collections

b file:linenr | add a break point
l . | show code at breakpoint
c-x a | toggle tui
c-x 2 | cycle through register, asm
c-l | redraw/clear screen
i b | show all break point infomation
p a | print variable a
n | next 
c | continues run til hit next break point
s | step into function
bt | print back trace or call stack

# Source

CPP Con 2015 Gdb
