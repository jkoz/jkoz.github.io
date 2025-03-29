---
layout: post
title: Playing with terminal colors
categories:
 -
---

## One liner for display color

```sh
for x in {0..8}; do for i in {30..37}; do for a in {40..47}; do echo -ne "\e[$x;$i;$a""m\\\e[$x;$i;$a""m\e[0;37;40m "; done; echo; done; done; echo ""
```

## Colorized text from pipe with sed

```sh
echo test | sed 's/^/\x1b[32m/; s/$/\x1b[0m/'
echo test | sed 's/^/\x1b[33m/; s/$/\x1b[0m/'

```
