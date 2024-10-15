---
title: Setup iMac WiFi on Linux
description: 'A few notes about setting up the wifi drivers for an iMac on Linux'
pubDate: 'Aug 21, 2024'
heroImage: '/blog-placeholder-3.jpg'
---

I'm running Linux on my 2012 27" iMac. The wifi drivers never work out of the box.

I've found that USB tethering my phone to a linux machine is a reliable source of temporary internet.

I got these commands from this [source](https://www.reddit.com/r/Ubuntu/comments/ks2c4d/wifi_driver_help_on_a_macbook_pro_from_late_2012/).

```
sudo apt install bcmwl-kernel-source
sudo modprobe -r wl
sudo modprobe wl
```

Running these commands on Pop!\_OS resulted in the list of wifi networks immediately working. I could connect to wifi without restarting the OS.

