---
title: 'My Helix Config'
description: 'My current configuration for the Helix editor.'
pubDate: 'Oct 12, 2024'
heroImage: '/blog-placeholder-2.jpg'
---

You can access your config by using the `:config-open` command.

You can apply changes to your config by using the `:config-reload` command.

```toml
theme = "base16_transparent"

[editor]
line-number = "relative"
mouse = true
rulers = [80, 120]

[editor.statusline]
center = ["version-control"]

[keys.normal]
# From https://www.youtube.com/watch?v=p3qvSz4RJts
C-g = [":new", ":insert-output lazygit", ":buffer-close!", ":redraw"]
```
