---
layout: post
title: Dirty way to build and run c code from command line
categories:
  -
---

#. Create a shell function

```sh
goc() {
    c99 -xc - -g -O2 -Wall -I/usr/include -lm -include math.h -include stdio.h -include stdlib.h -o /tmp/a.out; /tmp/a.out;
}
```

#. Use it

```sh
echo "int main() { int a[] = { 1, 2 }; printf(\"%lu\", sizeof(a)); return 0; }" | goc
```
