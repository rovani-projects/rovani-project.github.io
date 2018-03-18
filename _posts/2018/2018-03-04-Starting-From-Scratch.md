---
layout: post
title: Starting From Scratch - First Time Only
subtitle: A Highly Opinionated Guide to Using GitHub Pages, Visual Studio Code, Jekyll, Google Domains, and Cloudflare to Create a Basic Secure Website  
category: Guides
series: starting-from-scratch
tags:
- gitforwindows
- visualstudiocode
- ubuntuforwindows
- jekyllonwindows
---

Starting from a blank Windows 10 laptop, this is how we go about creating a secure, robust website. The steps in this post only have to be done the first time through (installing Visual Studio Code, creating a GitHub account, etc.). The following posts in the series will be about what we use to quickly get _something_ in front of a client. It is also how this website was originally built.

{::options parse_block_html="true" /}
Install Ubuntu for Windows
: 1. Install the [Windows Subsystem for Linux](https://docs.microsoft.com/en-us/windows/wsl/install-win10){:target="_blank"} (_this will require a restart_)
  1. Install [Ubuntu for Windows](https://www.microsoft.com/store/productId/9NBLGGH4MSV6){:target="_blank"} ![Ubuntu - Launch and Installing]({{ site.images}}/Ubuntu-launch.png)

Install [Git for Windows](https://git-scm.com/download/win){:target="_blank"}
: 1. Download the installer and start the setup.
  1. We like to keep everything up to date, so go ahead and check daily for updates. ![Git Setup - Components]({{ site.images }}/git-setup-components.png)
  1. Since we are going to install Visual Studio Code, that is a sensible default editor. ![Git Setup - Default Editor]({{ site.images }}/git-setup-default-editor.png)
  1. The default settings for the PATH environment works for our needs. ![Git Setup - Path]({{ site.images }}/git-setup-path.png)
  1. Using the native Windows library just seems sensible, right? ![Git Setup - Https Transport backend]({{ site.images }}/git-setup-https-transport.png)
  1. Leaving line endings as the default could cause some issues if you are using both a Windows machine and a Linux machine, but I prefer letting the environments sort it out, not Git. ![Git Setup - Line Endings]({{ site.images }}/git-setup-line-endings.png)
  1. MinTTY is a powerful tool, but keeping with the built-in terminal emulator means less components to install. ![Git Setup - Terminal Emulator]({{ site.images }}/git-setup-terminal.png)
  1. "Enable Git Credential Manager" is a setting that ends up being one of the most time-saving checkboxes. ![Git Setup - Extras]({{ site.images }}/git-setup-extras.png)

Download and Setup [Visual Studio Code](https://code.visualstudio.com) (a free, open source editor from Microsoft)
: 1. Download [Visual Studio Code installer](https://go.microsoft.com/fwlink/?Linkid=852157){:target="_blank"} for Windows.
  1. Technically, Jekyll could be installed using any terminal. However, I prefer to do it from within VS Code.
  1. Open a terminal (``` Ctrl+` ```) and follow the directions from [Jekyll on Windows](https://jekyllrb.com/docs/windows/#installation-via-bash-on-windows-10){:target="_blank"}

Create GitHub Accounts
: 1. GitHub makes signing up incredibly easy. Go to [https://github.com/join](https://github.com/join){:target="_blank"} and create an account.
{: .list }