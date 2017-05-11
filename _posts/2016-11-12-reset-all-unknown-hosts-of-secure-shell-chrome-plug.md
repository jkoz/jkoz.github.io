---
layout: post
title: Reset All Unknown Hosts of Secure Shell Chrome Plugin
categories:
  -
---

linux server changes RSA key, typically, ssh client will throw msg:

" WARNING: REMOTE HOST IDENTIFICATION HAS CHANGED"

solution is to reset that host or all hosts

1. ctrl+shift+j
2. run term_.command.removeAllKnownHosts()
