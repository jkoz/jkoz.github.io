---
layout: post
title: reset all unknown hosts of secure shell chrome plug
categories:
  -
---

linux server changes RSA key, typically, ssh client will throw msg:

" WARNING: REMOTE HOST IDENTIFICATION HAS CHANGED"

solution is to reset that host or all hosts

1. ctrl+shift+j
2. run term_.command.removeAllKnownHosts()
