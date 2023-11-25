---
layout: post
title: "Linux Mint Screen Off After Inactivity Manual Time Setting"
date: 2023-11-25
---

So here is a fun little one.

As I mentioned in my [previous post](https://martinsblog.github.io/blog/2023/11/22/lmde-live-USB-creation) I am now using Linux Mint Debian Edition (LMDE) for my operation system (on some computers). One little problem I have always had with Mint is the auto screen off after inactivity timing options. It is the only operation system I have ever used that does not provide a 1 minute option. The minimum time you can set in "Power Management" under "Preferences" is 5 minutes. But I want to have a 1 minute option available sometimes.

I started out by searching for "manual linux mint screen off" and ended up [here](https://forums.linuxmint.com/viewtopic.php?t=346700) which suggested a few different solutions. I tried some of the suggestions for using the xset command through terminal and found that the commmand "xset dpms force off" did in fact turn off my screen. So I went to "Keyboard" under "Preferences" and in the "Shortcuts" section setup a custom shortcut for that command bound to an otherwise unused key on my keyboard. This worked, but was not a true solution.

A couple days later I did a search for "xset command" to see if I could find something more suitable and I came across [this](https://wiki.archlinux.org/title/Display_Power_Management_Signaling). When I read "XScreenSaver and xfce4-power-manager use their own DPMS settings and override xset configuration." in a note toward the end of the page I realized to really fix my problem I would have to somehow change a setting in whatever package Mint used for power management.

So I right-clicked on "Power Management" in "Preferences" and clicked "Uninstall". This is the best way I know to figure out what package was being used. Mint comes up with a confirmation dialouge that tells you the package name. I found out that "Power Management" is part of the "Cinnamon" package. [Cinnamon](https://en.wikipedia.org/wiki/Cinnamon_(desktop_environment)) is the default desktop environment that Mint uses. I of course cancelled the uninstall.

This led me to a search for "Cinnamon power management" and [this](https://www.reddit.com/r/linuxmint/comments/efqb6g/system_settings_power_management) is what I found. Finally! The solution here was spot on. Now I could type "gsettings set org.cinnamon.settings-daemon.plugins.power sleep-display-ac 60" into the terminal and the screen would turn off automatically after 1 minute of inactivity (while plugged in, notice there is a different command used for the running on battery setting). I would bet that if I open back up "Power Management" under "Preferences" the setting would automatically get changed back to 5 minutes and I will have to run the command again, but I can deal with that.
