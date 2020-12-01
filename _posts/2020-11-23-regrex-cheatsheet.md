---
layout: post
title: Regrex cheatsheet
categories:
  -
---

# Dots

- A dot is a point, a point can point to anything
- \\ to escape a backslash for a dot, to make a dot unspecial 
 
# Optionals

- * : 0x1 = 0 (zeoro or more)
- + : 0+1 = 1 (one or more)
- ? : do you want it or not ?

# Greediness

- 1.*9 : match all, and stop
- 1.*?9 : match the minimum amount, and stop
- 1.+?9 : match 2 match, and stop
