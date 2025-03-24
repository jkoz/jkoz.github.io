---
layout: post
title: ssh agent passphrase
categories:
 -
---

## Start ssh-agent
```sh
eval "$(ssh-agent -s)"
```

## Add private key
```sh
ssh-add ~/.ssh/id_ed25519
```

