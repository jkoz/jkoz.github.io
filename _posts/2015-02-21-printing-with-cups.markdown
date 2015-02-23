---
layout: post
---

### Packages

```sh

yaourt -S cups-bjnp
pacman -S cups ghostscript gsfonts

pacman -S gutenprint # need to check this

```

### Start cups service:

```sh
systemctl start org.cups.cupsd.service
```

- Go to http://localhost:631/ add a printer (choose correct make)

