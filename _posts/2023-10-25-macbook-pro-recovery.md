---
layout: post
title: "2019 MacBook Recovery Mode and OS Upgrade From Flash Drive"
date: 2023-10-25
---

Recently I had a client who dropped off a MacBook Pro laptop. He said it was purchased in 2021 so I assumed that it was an [Apple silicon](https://en.wikipedia.org/wiki/Mac_transition_to_Apple_silicon) based computer. Mistake #1.

The first thing I wanted to do was to update the OS to [Ventura](https://en.wikipedia.org/wiki/MacOS_Ventura) using a USB flash drive. [See here](https://osxdaily.com/2022/12/12/how-to-create-a-bootable-macos-ventura-usb-install-drive/) for how to create such a drive. The laptop had [Catalina](https://en.wikipedia.org/wiki/MacOS_Catalina) on it at the time, which should have tipped me off that it in-fact was not a 2021 model. But I continued in my ignorance.

I shutdown the computer and after waiting a bit to make sure it was completely powered off I proceeded to hold in the power button. By holding the power button down when turning on a silicon-based Mac you start the computer in recovery mode. [See here](https://www.macrumors.com/how-to/enter-macos-recovery-mode-apple-mac/). It did not enter recovery mode when I did this. It just powered on and then back off with a beep. It finally dawned on me that maybe this *was not* a silicon-based Mac.

I went to Apples' [coverage check site](https://checkcoverage.apple.com) and entered the serial number located on the bottom of the laptop. This will tell you the year of manufacture and the warranty status. It turned out this was a 2019 model.

This time I held in the "Command" and the "R" keys at the same time while powering on the computer and succesfully entered recovery mode. [See here](https://osxdaily.com/2020/11/20/boot-mac-recovery-mode/).

The next step was to change some settings in the [startup security utility](https://support.apple.com/guide/security/startup-security-utility-secc7b34e5b5/web) so that I could boot from a USB drive. This is found in the "Utilties" menu when in recovery mode. I set the "Secure Boot" option to "Medium Security" and the "Allowed Boot Media" setting to "Allow booting from external or removable media". The computer will ask you for an Administrator password in order to complete these changes which should be the password for your user account that you use to login to your computer during normal startup. Finishing these steps I shutdown the computer.

Now to boot from the USB flash drive I held in the "Option" key while powering on the computer. When I clicked on the flash drive option it came up with a message that it had to run an update first. This was an online upate, so I hooked the computer to the internet. When I clicked "update" there was an error message and it would not continue. After some more fiddling around I figured out that the computer clock had the wrong date and time. This made sense since it had been sitting unused for so long with no battery charge. So after setting the correct time and date I ran the update succesfully.

I had to restart the computer once more and this time I was able to boot from the flash drive and run the update to macOS Ventura.
