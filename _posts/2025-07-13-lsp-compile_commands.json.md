---
layout: post
title: LSP compile_commands.json
categories:
 -
---

Use compiledb to parse output of make & generate compile_commands.json

```
make VERBOSE=y all &> mo.txt && compiledb --parse mo.txt
```
