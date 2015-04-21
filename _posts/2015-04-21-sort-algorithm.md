---
layout: post
title: Sort algorithm
categories:
  -
---

```python
def selection_sort(l):
    for i in range(len(l) - 1, -1, -1): # [len - 1, 0]
        largest = i
        for j in range(1, i + 1): # [1, i]
            if l[j] > l[largest]:
                largest = j
        l[largest], l[i] = l[i], l[largest]
```
