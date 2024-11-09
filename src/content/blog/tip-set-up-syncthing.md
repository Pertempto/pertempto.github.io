---
title: "Tip: Set Up Syncthing"
description: "How to set up syncthing on a ubuntu-based system for seamless file sync on your local network."
pubDate: "Nov 9, 2024"
heroImage: "/syncthing-logo.svg"
tags: "tips, homelab, linux"
---

## Background

I've heard about Syncthing many times, but I had never found the time to set it up. Recently I found myself needing to sync my `todo.txt` file between my laptop and my phone, in order to have access to my to-do list on both devices (more details about that system coming in a future post, hopefully). Syncthing is the perfect tool for the job. It can run on both my Linux and Android devices, and doesn't require any kind of centralized server. The setup takes a few steps, but really it's pretty simple.

## Steps

These steps should work on any Ubuntu-based system. I hope to write a future post about my adventures with using Syncthing on my Android device. If you are using a Windows device, are you a real engineer? 😜 You can find links for other platforms (including macOS and Windows) on the [downloads page](https://syncthing.net/downloads/).

### Install Syncthing
The `syncthing` package available by default on my system was quite outdated, but fortunately Syncthing has their own apt repository.

You can find the full steps [here](https://apt.syncthing.net/), but I'll include the basics here for completeness.

```sh
# Add the release PGP keys
sudo mkdir -p /etc/apt/keyrings
sudo curl -L -o /etc/apt/keyrings/syncthing-archive-keyring.gpg https://syncthing.net/release-key.gpg
# Add the "stable" channel to your APT sources
echo "deb [signed-by=/etc/apt/keyrings/syncthing-archive-keyring.gpg] https://apt.syncthing.net/ syncthing stable" | sudo tee /etc/apt/sources.list.d/syncthing.list
# Update and install syncthing
sudo apt-get update
sudo apt-get install syncthing
```

### Automatically Run Syncthing

Now you have the package installed, but you have to manually run the `syncthing` command in order to actually use it. This isn't ideal, because we want an automatic system that syncs our important files without us having to think about it.

The Syncthing docs include a great [page](https://docs.syncthing.net/users/autostart.html) with many ways to handle this.

I followed the steps to set up a `systemd` user service, which I will also include here. If you would like to set up a system-wide `systemd` service, or use some other strategy, please read the documentation. It really is quite easy to follow.

```sh
# Download the service file
curl -o ~/.config/systemd/user/syncthing.service https://raw.githubusercontent.com/syncthing/syncthing/refs/heads/main/etc/linux-systemd/user/syncthing.service
# Enable the service
systemctl --user enable syncthing.service
# Start the service
systemctl --user start syncthing.service
# Check the status of the service
systemctl --user status syncthing.service
```

### Sync a Folder

Once you have Syncthing running, you should be able to access the web interface from a web browser by going to [http://127.0.0.1:8384](http://127.0.0.1:8384).

You must first set up a remote device to share with, using the "Add Remote Device" button.

Once you have a remote device connected, use the "Add Folder" button to set up a folder to share between the devices. Syncthing will watch the folder for any changes, and sync those automatically between the devices.

## Future Possibilities

This is only the beginning of what you can do with Syncthing. I'm really excited about the possibilities this opens up.

Instead of relying on cloud services like Google Drive, Dropbox, or even GitHub to share files, we can sync files between devices without our data ever leaving our network. It's also nice to have my most-used files synced across many devices. If one device goes down, I should still have a very recent version (if not the newest version, depending on how recently Syncthing ran) of that file available on another device, with no manual effort of my own.

Here are a few of the things I want to explore further.
- Set up Syncthing with related tooling on Android in order to sync files to your mobile devices.
- Integrate with a Tailnet in order to sync your devices remotely, even when you aren't at home.
- Syncing configuration files between your different Linux devices.
- Improving security of my Syncthing setup.

## Credits

- https://apt.syncthing.net/
- https://docs.syncthing.net/users/autostart.html
- https://www.digitalocean.com/community/tutorials/workflow-downloading-files-curl
