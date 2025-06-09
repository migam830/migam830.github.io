---
layout: page
title: Random tips
permalink: /random-tips/
---
This page contains random tips and tricks. Basically, when I discover useful tips, I will put them here. Most things will be tech related but could include other topics as well. Some of these are likely to be very specific but I figure they might be useful in case someone else is in a similar situation.

Here are the random tips and tricks:

* If a website replaces the default right click menu with their own menu, holding shift while right clicking brings up the default menu
* You don't need a phone to generate 2FA (two-factor authentication) codes! You can also use a device that is offline. These codes are generated using a mathematical algorithm (TOTP), and all that algorithm needs is the current time and a secret string provided by the company. You can scan the QR code given to you with any app, script or browser extension that supports the TOTP algorithm. If you don't get a QR code when switching on 2FA, click "I'd like to use a different authenticator app" or similar and you should get a QR code. See [here](https://docs.github.com/en/authentication/securing-your-account-with-two-factor-authentication-2fa/configuring-two-factor-authentication) for more information.
* Vim has a built-in spell checker, just type `:set spell` to enable it
* In YouTube on a desktop, press `<` and `>` (without pressing shift) to move backwards and forwards by exactly one frame
* If you have a computer where you are unable to boot into its operating system, you might find [Super Grub2 Disk](https://www.supergrubdisk.org/super-grub2-disk/) useful. This is a bootable image which can boot most Linux and Windows operating systems.
* If you have a site that uses Jekyll and the Minima theme (like this site), don't use `h1` headings in your posts. This is because the page title is automatically made `h1` and using more `h1` headings causes `h1` headings to be smaller than `h2` headings. Start with `h2` headings and for subheadings use `h3`, `h4` etc.
* If a website has a paywall (or tries to make you pay to reject cookies), you might be able to get around this by disabling JavaScript. This only works some of the time, since some sites won't send the full content from their server until you log in. To do this, press F12 ([#F12IsNotACrime](https://www.youtube.com/watch?v=lSsvzBV0tyI)), click "settings" and scroll down until you see the option to disable JavaScript.
* You don't need to install Balena Etcher to burn an ISO file to a USB stick. You can just use core Linux commands like `cat`! See [this ArchWiki page](https://wiki.archlinux.org/title/USB_flash_installation_medium#Using_basic_command_line_utilities) for more info.
* Single quotes and double quotes are not the same in Bash. A string in single quotes will be interpreted literally and none of the characters will be replaced. Double quotes are very similar but will interpret the characters `$`, `` ` ``, `\` and `!` differently. See bash manual page for more details.
* You can officially dual-boot different versions of Android on some devices, possibly without needing to unlock the bootloader! See the Android documentation about [Dynamic System Updates](https://developer.android.com/topic/dsu) and [Generic System Images](https://developer.android.com/topic/generic-system-image/) for more details.
