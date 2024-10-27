---
title: "Tip: Adding a User to a Group on Linux"
description: "Something I should have learned a long time ago."
pubDate: "Oct 27, 2024"
heroImage: "/lemurs.jpg"
tags: "tips"
---

*This is the first of many short posts I intend to write with various tech tips I find useful. Hopefully they can also be useful to others. If not, at least I'll have something to refresh my memory in six months when I forget! 😅*

## Background

For some reason, I've never had the need to assign a user to a group on Linux. I came across the need this week while I was setting up my Debian 12 server. The `addison` user I created as part of the installation process was not part of the `sudo` group.

## Steps

1. Run `su` to login as the root user. You will be prompted to enter the root password.
2. Run `sudo usermod -aG <group-name> <user-name>`.
   - Replace `<group-name>` and `<user-name>` with the values relevant for your situation.
   - For example, I used `sudo usermod -aG sudo addison` to add the `addison` user to the `sudo` group.
3. Run `exit` to log out of the root user session.
4. You aren't quite done yet! Log out and log back in so that the changes can take effect.

After following these steps, I double-checked that `addison` had `sudo` access with `sudo apt update`. It worked! 🎉

You can also use the `groups` command to check which groups the current user is a part of.

## Credits

- Lemurs image from [NickyPe](https://pixabay.com/photos/ring-tailed-lemur-lemur-group-cub-6954076/)
- https://itslinuxfoss.com/add-user-sudoers-debian-12/
- https://linuxhandbook.com/check-group-of-user/
