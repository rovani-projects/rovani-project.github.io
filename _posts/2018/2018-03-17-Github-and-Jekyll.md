---
layout: post
title: Creating and Testing The Website
subtitle: A Highly Opinionated Guide to Using GitHub Pages, Visual Studio Code, Jekyll, Google Domains, and Cloudflare to Create a Basic Secure Website  
category: Guides
series: starting-from-scratch
tags:
- github
- googledomains
- jekyll
- cloudflare
---

Since this is a "Highly Opinionated Guide", all of the following is done strictly within Visual Studio code. Most of the terminal commands could be executed in a Windows terminal, but I like to keep it all in one place.

{::options parse_block_html="true" /}
Create GitHub Organization Account
: 1. Create an Organization Account - I recommend doing this so you can easily transfer it to someone else in the future, add other collaborators, and generally get more features than if it was just a personal account. ![GitHub - New Organization]({{ site.images }}/github-add-new.png)
  1. Fill out the form, picking a unique organization name, putting in any email for Billing, and selecting the Free plan. ![GitHub - Sign up your team]({{ site.images }}/github-sign-up-your-team.png)
  1. No need to add any collaborators as this time (you can always add people later).
  1. Create a new repository. ![GitHub - Create a new repository]({{ site.images }}/github-create-new-repo.png)
  1. Use the Owner plus "_.github.io_" as the Repository name, and do not initialize it. ![GitHub - Create a new repository]({{ site.images}}/github-create-new-repo-step.png)

Clone Jekyll Now, change remote, push to new repository
: 1. Open a terminal in Visual Studio Code (``` Ctrl+` ```)
  1. Go to the root folder of your repositories (```c:\Users\drovani\source\repos\```)
  1. Get a copy of the [Jekyll Now](https://github.com/barryclark/jekyll-now){:target="_blank"} code  
     ```
     git clone https://github.com/barryclark/jekyll-now.git
     ```
  1. Go into the folder  
     ```
     cd .\jekyll-now\
     ```
  1. Remove the current remote origin  
     ```
     git remote remove origin
     ```
  1. Add the github repository as origin  
     ```
     git remote add origin https://github.com/jekyll-right-now/jekyll-right-now.github.io.git
     ```
  1. Push repository to github  
     ```
     git push -u origin master
     ```  
     _The first time you do this, it will ask you to authentic with GitHub._
  1. Just to clean things up, rename the base directory  
      ```
      cd ..
      ren jekyll-now jekyll-right-now.github.io
      cd .\jekyll-right-now.github.io\
      ```
  1. Install necessary gems and serve up the site:  
      ```
      bash
      gem install jekyll-sitemap
      jekyll serve
      ```
  1. Open your browser to <http://127.0.0.1:4000> to verify that Jekyll is working locally.
  1. Open your browser to the GitHub Pages, to validate that it's working, too. ![Jekyll Right Now]({{ site.images }}/jekyll-now-first.png)
{: .list }

[jekyll-now]: <https://github.com/barryclark/jekyll-now>