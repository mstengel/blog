---
layout: post
title: Erstellung eines bootbaren USB-Mediums
categories: [snippet]
tags: [IT]
description: Eine Notiz für mich, wenn ich mal wieder ein Betriebssystem installieren möchte.
comments: true
---

**Update: Um ein bootbares Medium mit Windows 10 zu erstellen, klappt das nicht, wie bisher beschrieben. Unten wurde daher der Hinweis darauf ergänzt, die dann vorzugehen ist.**

## Pfad des USB-Sticks herausfinden

First plug in your USB-Stick.
Then type:

    lsblk

Your output should look something like this

    NAME   MAJ:MIN RM   SIZE RO TYPE MOUNTPOINT
    sda      8:0    0 465,8G  0 disk 
    ├─sda1   8:1    0  74,5G  0 part /
    ├─sda2   8:2    0 390,2G  0 part /home
    ├─sda3   8:3    0     1K  0 part 
    └─sda5   8:5    0     1G  0 part [SWAP]

Now you can use the size to determine which one is your usb stick . To mount it somewhere in your home folder for example just type:

    mkdir ~/UsbStick
    sudo mount /dev/PATH_TO_YOUR_STICK ~/UsbStick

obviously replacing `PATH_TO_YOUR_STICK` with the right `/dev/sdX` path and `~/UsbStick` with the directory you created using the `mkdir` command

[via [askubuntu.com](https://askubuntu.com/questions/311772/how-do-i-know-the-device-path-to-an-usb-stick#311775) ]

## Iso-Image bit-genau kopieren

Run the following command, replacing `/dev/sdx` with your drive, e.g. `/dev/sdb`. (Do not append a partition number, so do not use something like `/dev/sdb1`)

    dd bs=4M if=/path/to/archlinux.iso of=/dev/sdx status=progress oflag=sync

[via [archlinux.org](https://wiki.archlinux.org/index.php/USB_flash_installation_media) ]

## Windows-Installationsmedium

Ohne partition table und entsprechendem File-System geht da nichts. Daher hier zwei hilfreiche Links USB-Medien zu erstellen, die über MBR oder UEFI booten.

This guide works on any Linux distribution as long as it has GRUB and GParted installed and can make bootable USB for any Windows version newer than Vista: Windows Vista, Windows 7, Windows 8, Windows 8.1 and Windows 10. UEFI boot is only supported for Windows 7 x64 and newer: [Make a bootable Windows USB from Linux](https://www.onetransistor.eu/2014/09/make-bootable-windows-usb-from-ubuntu.html) [@onetransistor.eu](https://www.onetransistor.eu)

However that method is unusable in some cases where install.wim is larger than 4 GB. We will make two partitions on the USB drive, one that is FAT32 and will hold an EFI bootloader and the other is NTFS and holds Windows installation files. The bootloader will use a NTFS driver to read the NTFS partition and boot Windows. [UEFI NTFS: Bootable Windows USB from Linux](https://www.onetransistor.eu/2015/09/uefi-ntfs-bootable-windows-usb-linux.html) [@onetransistor.eu](https://www.onetransistor.eu)
