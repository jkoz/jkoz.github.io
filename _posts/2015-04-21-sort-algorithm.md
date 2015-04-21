---
layout: post
title: Sort algorithm
categories:
  -
---

#. Selection sort

```python
def selection_sort(l):
    for i in range(len(l) - 1, -1, -1): # [len - 1, 0]
        largest = i
        for j in range(1, i + 1): # [1, i]
            if l[j] > l[largest]:
                largest = j
        l[largest], l[i] = l[i], l[largest]
```

#. Insertion sort

```python
def insertion_sort(l):
    for i in range(1, len(l)): # [1, len - 1]
        pos, new = i, l[i]
        while pos > 0 and l[pos - 1] > new: # look for position to insert
            l[pos] = l[pos - 1]
            pos -= 1
        l[pos] = new
```
