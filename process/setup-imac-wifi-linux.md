I've found that USB tethering my phone to a linux machine is a reliable source of temporary internet.

https://www.reddit.com/r/Ubuntu/comments/ks2c4d/wifi_driver_help_on_a_macbook_pro_from_late_2012/

```
sudo apt install bcmwl-kernel-source
sudo modprobe -r wl
sudo modprobe wl
```

Running these commands on Pop!_OS resulted in the list of wifi networks immediately working. I could connect to wifi without restarting the OS.
