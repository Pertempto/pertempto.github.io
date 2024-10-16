---
title: 'My Helix Config'
description: 'My current configuration for the Helix editor.'
pubDate: 'Oct 12, 2024'
updatedDate: 'Oct 16, 2024'
heroImage: '/blog-placeholder-2.jpg'
---

You can access your config by using the `:config-open` command.

You can apply changes to your config by using the `:config-reload` command.

```toml
# config.toml

theme = "base16_transparent"

[editor]
line-number = "relative"
mouse = false
rulers = [80, 120]

[editor.file-picker]
hidden = false

[editor.soft-wrap]
enable = true

[editor.statusline]
center = ["version-control"]

[editor.lsp]
display-inlay-hints = true

[keys.normal]
# From https://www.youtube.com/watch?v=p3qvSz4RJts
C-g = [":new", ":insert-output lazygit", ":buffer-close!", ":redraw"]
```


```toml
# languages.toml

[[language]]
name = "markdown"
language-servers = [ "marksman", "ltex-ls" ]

[[language]]
name = "json"
indent = { tab-width = 4, unit = "    " }
```
