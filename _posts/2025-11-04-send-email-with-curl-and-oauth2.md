---
layout: post
title: Send email with curl and oauth2
categories:
 -
---

# oauth2 code

```sh
https://accounts.google.com/o/oauth2/auth?scope=https://mail.google.com&response_type=code&redirect_uri=urn:ietf:wg:oauth:2.0:oob&client_id=yci
```

# access_token (bearer), refresh_token

```sh
curl \
    -s https://accounts.google.com/o/oauth2/token \
    -d "client_id=yci" \
    -d "redirect_uri=urn:ietf:wg:oauth:2.0:oob" \
    -d 'grant_type=authorization_code' \
    -d 'code=yc' \
    -d 'client_secret=ycs'
```

# send email using bearer ${atk}

```sh
curl -sv --sasl-ir --ssl-reqd \
    --user "rn" \
    --oauth2-bearer "${atk}" \
    --url "smtp-server.com:587" \
    --mail-from "from@mail.com" \
    --mail-rcpt "rcpt@mail.com" \
    --upload-file /tmp/mail.md
```


