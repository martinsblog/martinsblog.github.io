---
layout: post
title: "Linux Mint Debian Edition Live USB Creation"
date: 2023-11-22
---

I was excited when the new edition of [Linux Mint Debian Edition](https://linuxmint.com/download_lmde.php) was released recently. I have been using [Sparky Linux](https://sparkylinux.org) for a while now but am happy to be getting back to Linux Mint.

The different kinds of Linux available can get confusing. There are many [distros](https://en.wikipedia.org/wiki/Linux_distribution) developed for all kinds of purposes. [Ubuntu](https://en.wikipedia.org/wiki/Ubuntu) is one of the best-known distros. It is based off of [Debian](https://en.wikipedia.org/wiki/Debian).

Linux Mint is specifically designed for users who are accustomed to Microsoft Windows. That's me! The default version of Linux Mint is based off of Ubuntu.

Ubuntu is developed and controlled by a company called [Canonical](https://en.wikipedia.org/wiki/Canonical_(company)). I have avoided using Linux Mint because of this. But with Linux Mint Debian Edition there is no Ubuntu involved. This distro is based directly off of Debian. Hooray!

The thing is I have been running into a problem when I try to install LMDE. Normally I use [Rufus](https://rufus.ie/en/) to create a live USB flash drive for installation. But every time I would run the install, after loading LMDE from the live USB, it would get most of the way through and then close without any kind of message before it finished. I figured it was either a corrupted ISO or a corruption on the flash drive. Or, I began to suspect, after verifying the ISO and creating the live USB multiple times, that I had a failing flash drive. But the same thing happened with a different flash drive. After giving up for a while I came back to it and finally tried using a different live USB creation program called [mkusb](https://help.ubuntu.com/community/mkusb). What tipped me off to what was happening was the warning mkusb gave me that the method of live USB creation I selected probably would not work because I was not using an Ubuntu-based distro. Ah-ha! So I selected a different method and it worked!

So in the end I learned that the regular way I created a live linux USB flash drive would not work with the LMDE ISO. At least, this specific version 6 of LMDE would not install correctly from the live USB that I created with Rufus. I had to use mkusb and select the "Cloning iso file" from the menu.

Unfortunately mkusb seems to only be easily available on Ubuntu and Sparky Linux. I am sure there are other ways of creating a fully functional live USB. Or you could burn the ISO to an actual DVD-R disc if you have access to an optical drive on the computer you are trying to get LMDE onto. Old school!
