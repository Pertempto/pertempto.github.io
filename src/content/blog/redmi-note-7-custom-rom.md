---
title: Redmi Note 7 Custom ROM
description: A few notes about getting a custom ROM working on a Redmi Note 7
pubDate: 'Sep 23, 2024'
heroImage: '/blog-placeholder-1.jpg'
---

I tried to install crDroid but I kept getting errors or boot loops.

Finally I followed the steps [here](https://xdaforums.com/t/rom-dynamic-partitons-lineageos-21-0-for-redmi-note-7-lavender.4680530/) and it worked.

Instead of `fastboot flash recovery recovery.img`

I used `sudo fastboot boot recovery.img`

I have to use `sudo` for fastboot for some reason, and I didn't want to mess with flashing the recovery when I could just boot it.

