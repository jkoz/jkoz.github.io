---
layout: post
title: Record a particular window with ffmpeg
categories:
  - video
---

```sh
ffmpeg -f x11grab -y -r 20 $(xwininfo -frame | xargs | sed -rne 's/.*Width: ([0-9]+).*Height: ([0-9]+).*Corners:.*\+([0-9]+)\+([0-9]+).*/-s \1x\2 -i :0.0+\3,\4/p') -f image2pipe -vcodec ppm - | convert -delay 5 - gif:- | gifsicle --colors 256 -O3 > new.gif
```
