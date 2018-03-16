---
layout: post
title: Starting From Scratch
subtitle: A Highly Opinionated Guide to Using Github Pages, Visual Studio Code, Jekyll, Google Domains, and Cloudflare to Create a Basic Secure Website  
category: Guides
tags:
- github
- googledomains
- jekyll
- cloudflare
---

Starting from a blank Windows 10 laptop, this is how we go about creating a secure, robust website. Some of the steps below only have to be done the first time through (installing Visual Studio Code, creating a Github account, etc.), but these steps are what we use to quickly get _something_ in front of a client. It is also how this website was originally built.

{::options parse_block_html="true" /}
Create Github and Github Organization Accounts
: 1. Github makes signing up incredibly easy. Go to [https://github.com/join][github-join]{:target="_blank"} and create an account.
  1. Create an Organization Account - I recommend doing this so you can easily transfer it to someone else in the future, add other collaborators, and generally get more features than if it was just a personal account. ![Github - New Organization]({{ site.images }}/github-add-new.png)
  1. Fill out the form, picking a unique organization name, putting in any email for Billing, and selecting the Free plan. ![Github - Sign up your team]({{ site.images }}/github-sign-up-your-team.png)
  1. No need to add any collaborators as this time (you can always add people later).
  1. Create a new repository. ![Github - Create a new repository]({{ site.images }}/github-create-new-repo.png)
  1. Use the Owner plus "_.github.io_" as the Repository name, and do not initialize it. ![Github - Create a new repository]({{ site.images}}/github-create-new-repo-step.png)

Install and Configure Visual Studio Code, Ubuntu for Windows, and bash (only has to be once)
: 1. Install the [Windows Subsystem for Linux](https://docs.microsoft.com/en-us/windows/wsl/install-win10) (_this will require a restart_)
  1. Install [Ubuntu for Windows](https://www.microsoft.com/store/productId/9NBLGGH4MSV6) ![Ubuntu - Launch and Installing]({{ site.images}}/Ubuntu-launch.png)
  1. Install [Git for Windows](https://git-scm.com/download/win) using the defaults - just keep clicking Next until the end.
  1. Download and Setup [Visual Studio Code](https://go.microsoft.com/fwlink/?Linkid=852157)
  1. Open a terminal (Ctrl + `) and follow the directions from [Jekyll on Windows](https://jekyllrb.com/docs/windows/#installation-via-bash-on-windows-10)

Clone Jekyll Now, change remote, push to new repository
: 1. Open a terminal in Visual Studio Code (Ctrl+`)
  1. Go to the root folder of your repositories (```c:\Users\drovani\source\repos\```)
  1. Get a copy of the [Jekyll Now](https://github.com/barryclark/jekyll-now) code  
     ```git clone https://github.com/barryclark/jekyll-now.git```
  1. Go into the folder ```cd .\jekyll-now\```
  1. Remove the current remote origin  ```git remote remove origin```
  1. Add the github repository as origin  
     ```git remote add origin https://github.com/jekyll-right-now/jekyll-right-now.github.io.git```
  1. Push repository to github ```git push -u origin master```  
     _The first time you do this, it will ask you to authentic with Github._
  1. Just to clean things up, rename the base directory
      1. ```cd ..```
      1. ```ren jekyll-now jekyll-right-now.github.io```
      1. ```cd .\jekyll-right-now.github.io\```
  1. A few last steps:
      1. ```bash```
      1. ```gem install jekyll-sitemap```
      1. ```jekyll serve```
      1. Open your browser to <http://127.0.0.1:4000>

Register Domain
: 1. Search for your domain on [Google Domains](https://domains.google.com/registrar#chp=sp&sp)
  1. Add one or more domains to your cart ![Google Domain Search]({{ site.images }}/google-search-domains.png)
  1. Proceed through Check out ![Google Domain Check out]({{ site.images }}/google-purchase-domains.png)

Create Cloudflare Account
: 1. Get nameservers
  1. Update Google Domains

Configure githubpages.io
: 1. Update CNAME

Configure DNS, HTTPS, HSTS, etc.
: 1. Secure all the things
  1. Page rules

{: .list }

[github-join]: <https://github.com/join?return_to=https%3A%2F%2Fgithub.com%2Forganizations%2Fnew&source=login>
[jekyll-now]: <https://github.com/barryclark/jekyll-now>