---
layout: post
title: Why I use Arch Linux
---
I have been using Arch Linux as my daily-driver desktop operating system for a few years now. I really like Arch, but whenever I talk to anyone about it, I inevitably make it seem like running Arch is very difficult and that you can't update your system without something breaking.

Obviously, different people have different preferences and I certainly wouldn't recommend Arch to everyone. However, using Arch isn't painful despite what people seem to think. If it was, I would have switched by now. There are many useful things that Arch has that are hard to come by in other distros. Here are the reasons why I have stuck with Arch for so long:

# Excellent documentation
Arguably the main reason I use Arch, is its documentation (ArchWiki), which is probably among the best documentation you can find on the internet.

ArchWiki documents just about every aspect of using the distro. If ArchWiki didn't exist, I definately wouldn't be using Arch. Yes, the installation process isn't very intuitive but ArchWiki documents every step of the process in great detail, making it easy for people who are proficient with Linux to find what they need. ArchWiki also has documentation for a lot of commonly used programs, telling you how to install, configure and use them. I have gotten into the habit of viewing the ArchWiki page for any program I am about to install since it saves me a lot of headaches later on.

# Up-to-date software
It has always baffled me why packages on most Linux distros (e.g. ubuntu, debian) are quite a few versions behind the latest release. This doesn't happen on any other OS. You always get the latest version of an app from its website on Windows and Google Play gives you the latest version on Android.

I understand that Linux distros often like things to be more stable to minimise the chance of crashes, but it makes getting the latest version annoying. For instance, to get the latest version of Python on Debian, you would have to use a third-party build or compile it from source, since the official website doesn't have Linux binaries. When I used Debian-based distros, I would often find myself downloading apps from their websites because I wanted the latest version. This isn't a massive issue but it makes your system harder to manage since you have to remember where you installed all your software.

This is what I love about Arch. The package manager (pacman) always provides the latest stable release so I can just use pacman to install everything, which makes finding and uninstalling apps much simpler. To emphasise, Arch provides the latest **stable** releases of software and not pre-release or alpha builds so things work as expected most of the time. I honestly think that things break for me on Arch about as rarely as they did when I used more stable distros, but now I can use the package manager to install almost everything which makes it easier to see what I have installed.

# Simple package format
If you want to see what I mean, look up how to create a DEB or RPM package and then look up how to create an Arch package. You will find that Arch uses a much simpler packaging than DEB or RPM. The final package file is literally just a tarball with the files you need for the package to run (binaries, config files etc.) and nothing else.

The build system used to create packages is also very simple. You can simply read one file (the `PKGBUILD`) and understand how the package is built. All the `PKGBUILD` files are available on the Arch website. I took all this for granted when I tried other distros, since finding build files can be much more complicated and even when I find them, those files are usually far more complicated than `PKGBUILD` files Arch uses. This makes troubleshooting issues easier if the issue is related to how the package was built.

# The Arch User Repository
As well as the official `core` and `extra` repositories, Arch has a collection of unofficial `PKGBUILD` files hosted on its website. This collection is known as the Arch User Repository, or AUR. Unlike the official repositories, the AUR does not host binary packages, just the scripts to build those packages, so some AUR packages might take a long time to install since they might require you to compile the source code.

This allows you to install almost any software fairly easily without needing to read the documentation on how to compile it. This can save you time if you are trying to install obscure software. However, anyone can submit a package to the AUR, so you should always read the `PKGBUILD` to check that the package is what it claims to be. Also, since the AUR is made up of user submissions, some packages may not build correctly. I find the AUR extremely useful, since it makes it easy to install almost any software as an Arch package.

I will note that I usually avoid using the AUR for software that has an updater built in (e.g. Firefox Nightly, Android Studio) since the updater can cause issues with updating the package by rebuilding it.


# Not tied to any desktop environment
Yes, you can install any desktop environment on any distro, but there are a lot of distros where nearly all their benefits are in the default desktop environment and installing anything else removes a lot of those benefits. On Arch, however, you can install any desktop environment or window manager you want and none of them are more official than any other. You just find the right page on ArchWiki and follow the instructions on how to install and configure whatever graphical interface you want.

Also, switching desktop environments is easy since you always know how you installed and setup your current one.

# Should you switch to Arch?
If you have made it to the end of this unnecessarily long post, you might be wondering if you should switch to Arch Linux. If the benefits I have described sound like they would benefit you, then perhaps you should give it a try. Maybe try installing Arch in a virtual machine to get familiar with the installation process and to see if you like it. You might find yourself needing to fix things every now and then, but ArchWiki and the Arch forums will likely be able to help you.

Even if you only install Arch in a virtual machine and use it for a short period of time, it will be worth it, since you will learn more about Linux in general and might find it easier to fix things on other distros.

If you have been reading this thinking "Why would anyone want this?" then probably stick with your current distro. If you're not currently running Linux, then I would recommend trying Linux Mint.
