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

Starting from a blank Windows 10 laptop, this is how I go about creating a secure, robust website. Many of the steps below only have to be done the first time through (installing Visual Studio Code, creating a Github account, etc., but these steps are what we use to quickly get _something_ in front of a client. It is also how this website was originally built.

{::options parse_block_html="true" /}
Create Github and Github Organization Accounts
: 1. Github makes signing up incredibly easy. Go to [https://github.com/join][github-join]{:target="_blank"} and create an account.
  1. Create an Organization Account - I recommend doing this so you can easily transfer it to someone else in the future, add other collaborators, and generally get more features than if it was just a personal account. ![Github - New Organization]({{ site.assets }}/images/github-add-new.png)
  1. Fill out the form, picking a unique organization name, putting in any email for Billing, and selecting the Free plan. ![Github - Sign up your team]({{ site.assets }}/images/github-sign-up-your-team.png)
  1. No need to add any collaborators as this time (you can always add people later).

Fork Jekyll Now
: 1. Open the [Jekyll Now Github][jekyll-now] page and click the Fork button. ![Github - Fork]({{ site.assets }}/images/github-fork.png)
  1. Select your new organization and then let Github do its thing. After a brief pause, you'll now have your forked version of Jekyll Now ![Github - Forked Jekyll Now]({{ site.assets }}/images/github-forked-jekyll-now.png)

Install and Configure Visual Studio Code
: 1. Download [Visual Studio Code](https://go.microsoft.com/fwlink/?Linkid=852157)
  1. Install [Ubuntu for Windows](https://www.microsoft.com/store/productId/9NBLGGH4MSV6)
  1. Install Jekyll with _bash_
  1. Configure git (credential manager)

Clone, mirror, check-in githubpages.io
: 1. Using Visual Studio, _git clone_
  1. Then _git mirror_
  1. Then _git push_

Register Domain
: 1. Search for your domain on [Google Domains](https://domains.google.com/registrar#chp=sp&sp)
  1. Add one or more domains to your cart ![Google Domain Search]({{ site.assets }}/images/google-search-domains.png)
  1. Proceed through Check out ![Google Domain Check out]({{ site.assets }}/images/google-purchase-domains.png)

Create Cloudflare Account
: 1. Get nameservers
  1. Update Google Domains

Configure githubpages.io
: 1. Update CNAME

Configure DNS, HTTPS, HSTS, etc.
: 1. Secure all the things
  1. Page rules

Customize Jekyll Now instance
: 1. Social accounts
  1. Forked as _Jekyll Right Now_

Test website with _jekyll serve_
: 1. Verify it works

Push changes to Github
: 1. _git push_
  1. Verify build status
  1. Smile
{: .list }

[github-join]: <https://github.com/join?return_to=https%3A%2F%2Fgithub.com%2Forganizations%2Fnew&source=login>
[jekyll-now]: <https://github.com/barryclark/jekyll-now>