---
layout: post
title: Auto Create Jekyll Post
categories:
 -
---

# One liner to create post for Jekyll
```sh
pst=`echo "This is my new title|/home/tait/gh/jkoz.github.io/_posts/" | awk -F "|" '{tt=$1; gsub(" ", "-", tt); fn=$2 strftime("%Y-%m-%d-") tolower(tt) ".md"; print "---\nlayout: post\ntitle: " $1 "\ncategories:\n -\n---\n" > fn}; END{ print fn }'` && vim -c ':norm! zRG' +start $pst
```
