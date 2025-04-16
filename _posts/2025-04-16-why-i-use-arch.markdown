---
layout: post
title: Why I use Arch Linux
---
I have been using Arch Linux as my daily-driver desktop operating system for a few years now. I really like Arch, but whenever I talk to anyone about it, I inevitably make it seem like running Arch is very difficult and that you can't run update your system without something breaking.

Obviously, different people have different preferences and I certainly wouldn't recommend Arch to everyone. However, using Arch is nowhere near as painful as people seem to think. If it was, I would have switched by now. There are many useful things that Arch has that are hard to come by in other distros. Here are the reasons why I have stuck with Arch for so long:

# New package versions
It has always baffled me why packages on most Linux distros (e.g. ubuntu, debian) are quite a few versions behind the latest release. This doesn't happen on any other OS. You always get the latest version downloading from an app's website on Windows and Google Play gives you the latest version on Android.

I understand that Linux distros often like things to be more stable to minimise the chance of crashes, but it makes getting the latest version annoying. For instance, to get the latest version of Python on Ubuntu, you would have to use a third-party build or compile it from source, since the official website doesn't have Linux binaries. When I used Debian-based distros, I would often find myself downloading apps from their websites because I wanted the latest version. This isn't a massive issue but makes it hard to remember where you installed the software.

This is what I love about Arch. The package manager (pacman) always provides the latest stable release so I can just use pacman to install everything, which makes finding and uninstalling apps much simpler. As I just said, Arch provides the latest **stable** release of software, not pre-release or alpha builds so things work as expected most of the time. I honestly think that things break for me on Arch about as rarely as they did when I used more stable distros.

# Simple package format
If you want to see what I mean, look up how to create a DEB or RPM package and then look up how to create an Arch package. You will find that Arch uses a much simpler packaging than DEB or RPM. The final package file is literally just a tarball with the files you need for the package to run (binaries, config files etc.) and nothing else.

The build system used to create packages is also very simple. You can simply read one file (the `PKGBUILD`) and understand how the package is built. All the `PKGBUILD` files are available on the Arch website. I took all this for granted when I tried other distros, since finding build files can be much more complicated and even when I find them, those files are usually far more complicated than `PKGBUILD` files Arch uses.

This makes troubleshooting issues easier if the issue is related to how the package was built.

# Excellent documentation
Arguably the main reason I use Arch, is its documentation (ArchWiki), which is probably among the best documentation you can find on the internet.

ArchWiki documents just about every aspect of using the distro. If ArchWiki didn't exist, I definately wouldn't be using Arch. Yes, the installation process isn't very intuitive but ArchWiki documents every step of the process in great detail, making it easy for people who are proficient with Linux to find what they need. ArchWiki also has documentation for a lot of commonly used programs, telling you how to install, configure and use them. I have gotten into the habit of viewing the ArchWiki page for any program I am about to install since it saves me a lot of headaches later on.

# Not tied to any desktop environment
Yes, you can install any desktop environment on any distro, but there are a lot of distros where nearly all their benefits are in the default desktop environment.
