---
title: Helix - Status Update 1
description: 'A few notes after 11 days of using Helix'
pubDate: 'Oct 16, 2024'
heroImage: '/blog-placeholder-1.jpg'
---

Helix has been great! I've got it installed on all my regularly-used machines now, and learning new motions and shortcuts is coming along quite nicely.

## Language Servers

This is one of the most important things to configure in order to use Helix for coding. Helix makes it [quite easy](https://docs.helix-editor.com/languages.html) to integrate with existing language servers. It comes with a bunch of [language preconfigured](https://docs.helix-editor.com/lang-support.html) (you can list them by running the very helpful `hx --health`), usually all that is required is installing the required language server binary on your system.

So far the only language servers I've really needed are [marksman](https://github.com/artempyanykh/marksman) and [typescript-language-server](https://github.com/typescript-language-server/typescript-language-server).

One other language server I would highly recommend is [ltex-ls](https://github.com/valentjn/ltex-ls). It's made for latex, but supports markdown too. I installed it for the spell checker, but its grammar suggestions have been very useful!

## Keyboard Shortcuts

I'm still very early in my journey of learning the Helix keyboard motions and shortcuts. For now I just stumble along with the ones I know, and over time I hope to pick up some of the more complicated ones that can improve my efficiency further.

Here are a few of my favorites

- `w`
	- Select next word
- `b`
	- Select previous word
- `x`
	- Select an entire line
- `c`
	- Change the given selection (delete it and then go into insert mode)
- `y`
	- Copy the selection
- `p`
	- Paste the selection
- `o`
	- Create a new line below the current line, then go into insert mode.
	- I was so excited when I found this one! It saves a ton of time when working in Markdown documents, when I want most of my new content to go on new lines instead of on the current line.
- `Space f`
	- Opens the file picker, with built-in fuzzy finding.
- `Space /`
	- Global search - this is really fast. Usually I just open helix in my top level `repos` directoy and then use the file picker and global search to jump around between files.
- `gd`
	- Go to definition
- `Ctrl+w v`
	- Open a split window to the right.
- `Ctrl+w Ctrl+w`
	- Move focus between windows.

There are many, many more - these are just a few of the ones that I use very regularly.

## Pain Points

My main pain point so far was when I tried to edit a JSON file, and Helix decided to totally change the indentation. I didn't have time to figure this out, so it was the one time I had to fall back to VS Code to get done what I needed to get done. I guess I need to learn more about the formatting tooling in Helix. It seems that some sort of auto-formatting was getting applied when I saved the file. 

## Next Up

Helix is now a normal part of my workflow. I am confident enough in using it that I am in the process of removing VS Code from all my machines. There is a learning curve with Helix and modal editing in general, but I think I'm comfortably started on the curve and I'm looking forward to getting to know it better.

A few tech-related things I'm looking forward to learning about soon

- [Imminch] - I would really like to get my family's photos off of Google Photos as soon as possible, mostly for privacy's sake. I ordered an $80 mini PC (a Lenovo Thinkcentre M715Q to be exact) off of ebay with the main purpose of running an Imminch instance. I'm looking forward to using a distributed mini-PC approach for my homelab setup, currently my homelab mostly consists of an old desktop PC running a bunch of Docker containers.
- [Astro](https://astro.build/) - My good friend [Leandro Méndez](leandez.netlify.app) recommended that I use Astro for my blog. The migration process was pretty simple. I'm excited to explore some of its more advanced features in the coming months. The ability to integrate with web frameworks like Angular or Vue looks really interesting.
