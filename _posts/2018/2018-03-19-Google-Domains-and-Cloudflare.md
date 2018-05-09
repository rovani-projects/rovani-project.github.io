---
layout: post
title: Registering the Domain and Securing the Website
subtitle: A Highly Opinionated Guide to Using GitHub Pages, Visual Studio Code, Jekyll, Google Domains, and Cloudflare to Create a Basic Secure Website
category: Guides
series: starting-from-scratch
tags:
- github
- googledomains
- cloudflare
---

The previous post covered creating a website. Everything to this point has been completely free, with the only investment being time. Now comes the one piece in the whole series were it costs something - registering the domain. We debated whether this actually comes first in the process - since knowning the domain name could drive the decisions for what the GitHub Organization name is, which in turn drives the name of the repository. However, it really doesn't matter, since the domain name and the GitHub account name have no dependancies on each other.


{::options parse_block_html="true" /}
Register Domain
: 1. Search for your domain on [Google Domains](https://domains.google.com/registrar#chp=sp&sp){:target="_blank"}
  1. Add one or more domains to your cart ![Google Domain Search]({{ site.images }}/google-search-domains.png)
  1. Proceed through Check out ![Google Domain Check out]({{ site.images }}/google-purchase-domains.png)

Protect the Site with Cloudflare
: 1. Create an account at [Cloudflare](https://www.cloudflare.com/a/sign-up){:target="_blank"}
  1. Click the ``` + Add Site ``` link, then enter the domain. ![Cloudflare - Add your site]({{site.images}}/cloudflare-add-site.png)
  1. Select the <span style="font-variant: small-caps">free</span> plan. ![Cloudflare - Select a Plan]({{site.images}}/cloudflare-select-plan.png)
  1. Add the <span style="font-variant: small-caps">cname</span> record, mapping ```www``` to the ```github.io``` domain. ![Cloudflare - Verify DNS]({{site.images}}/cloudflare-verify-dns.png)
  1. Cloudflare will now display the nameservers that they want this site to use. ![Cloudflare - Update Nameservers]({{site.images}}/cloudflare-update-nameservers.png)
  1. Go back to [Google Domains](https://domains.google.com/registrar) and enter the DNS settings for the domain. ![Google Domains]({{site.images}}/google-domain-list.png)
  1. Change the Name servers to **Use custom name servers** and copy the name servers that Cloudflare provided. ![Google - Custom name servers]({{site.images}}/google-custom-nameservers.png)
  1. Final piece is to update the <span style="font-variant: small-caps">cname</span> file in the GitHub repository. Conveniently, GitHub has a UI to do just this specific task. Go back to the repository and switch to the **Settings** tab. ![GitHub - Settings]({{site.images}}/github-settings.png)
  1. Scroll down to the **GitHub Pages** sections, and update the **Custom domain**. ![GitHub - Custom Domain]({{site.images}}/github-custom-domain.png)
  1. Click the **Save** button, which will check-in a commit to the <span style="font-variant: small-caps">cname</span> file, adding the domain as the only data in it.

Secure the Site with Cloudflare
: 1. Go to the **Crypto** page ![Cloudflare - Crypto]({{site.images}}/cloudflare-crypto.png)
  1. Set the **SSL** to **Full**. Do not set it to _Full (strict)_. ![Cloudflare - Crypto SSL]({{site.images}}/cloudflare-crypto-ssl.png)
  1. Set the **Always use HTTPS** to **On**. ![Cloudflare - Crypto HTTPS]({{site.images}}/cloudflare-crypto-https.png)
  1. Set the **Enable** button for **HTTP Strict Transport Security (HSTS)** ![Cloudflare - Crypto HSTS]({{site.images}}/cloudflare-crypto-hsts.png)
  1. Change all of the settings to **On**. ![Cloudflare - Crypto HSTS Settings]({{site.images}}/cloudflare-crypto-hsts-settings.png)
  1. Set the **Automatic HTTPS Rewrites** to **On**. ![Cloudflare - Crypto Automatic HTTPS]({{site.images}}/cloudflare-crypto-automatic-https.png)
  1. Go to the **Page Rules** page ![Cloudflare - Page Rules]({{site.images}}/cloudflare-pagerules.png)
  1. Add a rule for the root of the domain (note the trailing astericks), set **Cache Level** to **Cache Everything** ![Cloudflare - Page Rules Cache Level]({{site.images}}/cloudflare-pagerules-cachelevel.png)
  1. To redirect all traffic from the <span style="font-variant: small-caps">www</span> subdomain to the root URL, add a **Forwarding URL** rule. ![Cloudflare - Page Rules Fowarding URL]({{site.images}}/cloudflare-pagerules-forwarding.png)
  1. To ensure that any request via <span style="font-variant: small-caps">http</span> always redirects to the secure site, add a **Always Use HTTPS** rule. ![Cloudflare - Page Rules Always Use HTTPS]({{site.images}}/cloudflare-pagerules-alwaysusehttps.png)
  1. Order matters for these rules, so ensure they are in the order listed above. ![Cloudflare - Page Rules Order]({{site.images}}/cloudflare-pagerules-order.png)
{: .list }

It may take a few minutes or sometimes hours for all of these settings to propagate through the universe and reach its way back to the browser. Go make a sandwich, take care of some emails, and come back later. Bring up your site, and all should be well.