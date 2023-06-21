# [openwrt - how to install openwrt on bare metal](https://tom-sapletta-com.github.io/openwrt/)
how to install openwrt on bare metal


![image](https://github.com/tom-sapletta-com/openwrt/assets/5669657/53958051-5f2e-43bc-9de0-9da91acae2ea)

‎ACEMAGICIAN device

+ [Amazon.com: ACEMAGICIAN Mini PC T8 Pro, Intel Celeron N5095 (up to 2.90GHz), HDMI 4K@60 3 Screen Display, Dual Ethernet Ports, 8GB DDR4 RAM 256GB SSD Micro Desktop Computer, Windows 11 Pro, 2.4/5G WiFi, BT4.2 : Electronics](https://www.amazon.com/ACEMAGICIAN-Celeron-2-90GHz-Ethernet-Computer/dp/B0BMQ16KMN)


+ [T8Pro – ACEMAGICIAN](https://www.acemagic.com/pages/t8pro?_pos=1&_sid=20033dc9b&_ss=r)


![image](https://github.com/tom-sapletta-com/openwrt/assets/5669657/f65e10a0-bff8-4321-be56-bf0d09e2bf84)

+ [Ace Magician T8Pro review: Budget mini PC for office use - NotebookCheck.net Reviews](https://www.notebookcheck.net/Ace-Magician-T8Pro-review-Budget-mini-PC-for-office-use.680190.0.html)




download

![image](https://github.com/tom-sapletta-com/openwrt/assets/5669657/03642113-2375-4578-815d-3e701ebd5e2e)

generic-ext4-combined-efi.img.gz
+ [Index of /releases/22.03.5/targets/x86/64/](https://downloads.openwrt.org/releases/22.03.5/targets/x86/64/)


login
+ [[OpenWrt Wiki] Log into your router running OpenWrt](https://openwrt.org/docs/guide-quick-start/walkthrough_login)


clone partition from USB device
+ [[OpenWrt Wiki] Command-line interpreter](https://openwrt.org/docs/guide-user/base-system/user.beginner.cli)
+ [How to use DD to clone a partition off a disk image? - Unix & Linux Stack Exchange](https://unix.stackexchange.com/questions/73125/how-to-use-dd-to-clone-a-partition-off-a-disk-image)


## resize partition
[[HOWTO] Resizing root partition on x86 - Installing and Using OpenWrt - OpenWrt Forum](https://forum.openwrt.org/t/howto-resizing-root-partition-on-x86/140631)

```sh
BOOT="$(sed -n -e "/\s\/boot\s.*$/{s///p;q}" /etc/mtab)"
DISK="${BOOT%%[0-9]*}"
PART="$((${BOOT##*[^0-9]}+1))"
ROOT="${DISK}${PART}"
LOOP="$(losetup -f)"
losetup ${LOOP} ${ROOT}
fsck.ext4 -y -f ${LOOP}
resize2fs ${LOOP}
reboot
```

script: 
resize.sh

```sh
#!/bin/sh
echo -n "$(sed -n -e "/\s\/boot\s.*$/{s///p;q}" /etc/mtab)" > bootdisk.txt
BOOT=$(cat bootdisk.txt)
echo $BOOT

DISK=${BOOT%%[0-9]*}
PART=$((${BOOT##*[^0-9]}+1))
echo -n "${DISK}" > rootdisk.txt
echo -n "${PART}" >> rootdisk.txt
ROOT=$(cat rootdisk.txt)
echo $ROOT

LOOP=$(losetup -f)
echo ${LOOP} ${ROOT}

losetup ${LOOP} ${ROOT}
fsck.ext4 -y -f ${LOOP}
resize2fs ${LOOP}
reboot
```

