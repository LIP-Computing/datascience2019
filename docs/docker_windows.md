---
title: Use docker with Windows
layout: default
---

# Using docker with Windows

## 1 - Check your Windows version

To check your Windows version click the Windows key + r. In the prompt enter the following command:

```
winver
```

* If your Windows version is Pro or Enterprise you are ready to install Docker. Go to https://www.docker.com/ and follow the instructions to download and install.

* If your Windows version in Windows Home there are a few steps to follow:

Check if virtualization is active

ctrl+alt+delte to check the performance tab, check CPU, bottom right corner to see if virtualization is active.

To turn it on:

** HP **

> While rebooting, repeatedly click the Esc key to get into BIOS settings.
Press F10 to check BIOS configuration (follow instructions in the screen). 
Right key to System Configuration, go to Virtualization and press Enter.
Press F10, select Yes and press Enter to save changes and reboot

** Dell, Lenovo, Asus, Acer **

> Press F2 to check BIOS configuration.
Press the right key to Advanced options, select Virtualization Technology and press Enter to enable.
Select Activacte and press Enter.
Press F10, select Yes and press Enter to save changes and reboot

Some details may vary for different machines.

## 2- Download Virtualbox

Go to https://www.virtualbox.org/wiki/Downloads and use the download link for windows hosts

## 3 - Install Virtualbox

## 4 - Install Docker in the virtual machine

Choose your favourite Linux distribution (if no particular favourite, choose Ubuntu). Once running Linux install Docker with the normal instructions provided at https://www.docker.com/.

[back](./)
