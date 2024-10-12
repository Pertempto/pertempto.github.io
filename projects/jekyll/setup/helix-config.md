---
title: Helix Config
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
# Use system clipboard
y = "yank_main_selection_to_clipboard"
p = "paste_clipboard_before"
# From https://www.youtube.com/watch?v=p3qvSz4RJts
C-g = [":new", ":insert-output lazygit", ":buffer-close!", ":redraw"]
```
