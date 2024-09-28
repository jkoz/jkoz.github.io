---
layout: post
title: Bluetooth with bluez
categories:
  - cli, bluez
---


# Connect to a Bluetooth device

``` bash
sudo systemctl start bluetooth

bluetoothctl
scan on
devices
pair ID
trust ID
connect ID

```

