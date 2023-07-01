# [openwrt - how to install openwrt on bare metal](https://tom-sapletta-com.github.io/openwrt/)
how to install openwrt on bare metal


![image](https://github.com/tom-sapletta-com/openwrt/assets/5669657/53958051-5f2e-43bc-9de0-9da91acae2ea)

‎## ACEMAGICIAN device

+ [Amazon.com: ACEMAGICIAN Mini PC T8 Pro, Intel Celeron N5095 (up to 2.90GHz), HDMI 4K@60 3 Screen Display, Dual Ethernet Ports, 8GB DDR4 RAM 256GB SSD Micro Desktop Computer, Windows 11 Pro, 2.4/5G WiFi, BT4.2 : Electronics](https://www.amazon.com/ACEMAGICIAN-Celeron-2-90GHz-Ethernet-Computer/dp/B0BMQ16KMN)


+ [T8Pro – ACEMAGICIAN](https://www.acemagic.com/pages/t8pro?_pos=1&_sid=20033dc9b&_ss=r)


![image](https://github.com/tom-sapletta-com/openwrt/assets/5669657/f65e10a0-bff8-4321-be56-bf0d09e2bf84)

+ [Ace Magician T8Pro review: Budget mini PC for office use - NotebookCheck.net Reviews](https://www.notebookcheck.net/Ace-Magician-T8Pro-review-Budget-mini-PC-for-office-use.680190.0.html)


## download

![image](https://github.com/tom-sapletta-com/openwrt/assets/5669657/03642113-2375-4578-815d-3e701ebd5e2e)

generic-ext4-combined-efi.img.gz
+ [Index of /releases/22.03.5/targets/x86/64/](https://downloads.openwrt.org/releases/22.03.5/targets/x86/64/)


login
+ [[OpenWrt Wiki] Log into your router running OpenWrt](https://openwrt.org/docs/guide-quick-start/walkthrough_login)


clone partition from USB device
+ [[OpenWrt Wiki] Command-line interpreter](https://openwrt.org/docs/guide-user/base-system/user.beginner.cli)
+ [How to use DD to clone a partition off a disk image? - Unix & Linux Stack Exchange](https://unix.stackexchange.com/questions/73125/how-to-use-dd-to-clone-a-partition-off-a-disk-image)



## resize partition

[https://github.com/tom-sapletta-com/disk-resize](https://github.com/tom-sapletta-com/disk-resize)


## Virtualisation LXC

+ [LXD - success on OpenWRT (privileged containers) - but problems with unprivileged - LXD - Linux Containers Forum](https://discuss.linuxcontainers.org/t/lxd-success-on-openwrt-privileged-containers-but-problems-with-unprivileged/1729/6)
+ [cvmiller/openwrt-lxd: Directions and script for running OpenWrt on LXD](https://github.com/cvmiller/openwrt-lxd)
+ [Installing OpenWRT In Proxmox LXC – Virtualize Everything](https://virtualizeeverything.com/2022/05/23/setting-openwrt-in-proxmox-lxc/)\
+ [[OpenWrt Wiki] OpenWrt in LXC containers](https://openwrt.org/docs/guide-user/virtualization/lxc)



## Network


Here is how you can reload /etc/network/interfaces.

```
sudo service networking restart
```





