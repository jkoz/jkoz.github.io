---
layout: post
title: Essential vim keys
categories:
  -
---

# Fugitive

- do - get changes from other window to current
- dp - put changes current window to other
- ]c - jump to next change
- [c - jump to previous change

# Fold

- zf - create selected fold
- zd - delete current fold

# surround

- insert mode: C-g S {

# windows

c-w o | focus on current window, close other
c-w hjkl | move into window in given direction
c-w HJKL | move window in given direction
c-w 2+ | adjust size of current window 2 line
c-w _ | increase a window to maximum height
c-w \| | increase a window to maximum width

# Retab

```
:set tabstop=4 shiftwidth=4 expandtab
:retab
```
