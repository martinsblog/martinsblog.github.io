---
layout: post
title: "Linux Mint Debian Edition Install Issue"
date: 2023-11-22
---

I was excited when the new edition of [Linux Mint Debian Edition](https://www.linuxmint.com/download_lmde.php) was released recently. I have been using [Sparky Linux](https://en.wikipedia.org/wiki/SparkyLinux) for a while now but am happy to be getting back to Linux Mint. It is specifically designed for users who are accustomed to Microsoft Windows. That's me!

The different kinds of Linux available can get confusing. There are many [distros](https://en.wikipedia.org/wiki/Linux_distribution) developed for all kinds of purposes.

The default version of Linux Mint is based off of [Ubuntu](https://en.wikipedia.org/wiki/Ubuntu) which in turn is based off of [Debian](https://en.wikipedia.org/wiki/Debian). Ubuntu is developed and controlled by a company called [Canonical](https://en.wikipedia.org/wiki/Canonical_(company)). I have avoided using Linux Mint because of this. But with Linux Mint *Debian Edition* Ubuntu is not involved. This distro is based directly off of Debian. Hooray!

But I was having a problem trying to install LMDE. Every time I would load LMDE from the live USB on a new system and run the install it would get most of the way through and then close without any warning before finishing. I figured it was either a corrupted ISO or a corruption on the flash drive. Or, I began to suspect, after verifying the ISO and creating the live USB multiple times, that I had a failing flash drive. But the same thing happened with a different flash drive.

After giving up for a while I came back to it. Normally I use [Rufus](https://rufus.ie/en/) to create a live USB flash drive for installation. This time I tried using a different live USB creation program called [mkusb](https://help.ubuntu.com/community/mkusb). What tipped me off to what was happening was the warning mkusb gave me that the method of live USB creation I selected probably would not work because I was not using an Ubuntu-based distro. Ah-ha, perhaps Rufus was not working for the same reason! So I selected "Cloning iso file" in mkusb and it worked!

In the end I found that LMDE version 6 would not install correctly from the live USB that I created with Rufus. Unfortunately mkusb seems to only be easily available on Ubuntu and Sparky Linux. I am sure there are other ways of creating a fully functional live USB. I will update here if I learn of any.

Or you could burn the ISO to a DVD-R disc if you have access to a DVD writer drive. Old school!
