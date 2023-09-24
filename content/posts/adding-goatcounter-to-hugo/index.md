---
title: Adding GoatCounter to Hugo
slug: adding-goatounter-to-hugo
summary: GoatCounter is a web analytics platform that aims at offering easy to use and meaningful privacy-friendly web analytics as an alternative to Google Analytics or Matomo.
description: 
date: 2023-09-10T20:02:27+03:00
categories: []
tags: [Web Analytics]
draft: false
---

## Intro
I just posted about how I created this site with Hugo [here]({{< ref "/posts/how-i-created-my-site" >}}).

After careful consideration, I began to feel a strong inclination to substitute Google Analytics with a less invasive alternative, `GoatCounter`.

### Why GoatCounter?

GoatCounter is an [open source](https://github.com/arp242/goatcounter) web analytics platform available as a free hosted service or self-hosted app. 

It aims at offering easy to use and meaningful privacy-friendly web analytics as an alternative to Google Analytics or Matomo.

#### Key features

1. **Respects Your Privacy**: GoatCounter doesn't spy on users or use any special codes to identify them, so you don't need to show those annoying GDPR notices. You can control what data it collects.

2. **Lightweight and Fast**: It's like adding a tiny 3.5KB weight to your website. There's also a way to use it without JavaScript, and you can set it up in various ways.

3. **Counts Visitors Without Cookies**: GoatCounter can tell when someone visits your site without using cookies or any personal info.

4. **Keeps Useful Info**: It tracks things like what web browser visitors use, where they're located, and how big their screens are. It also keeps tabs on which websites brought people to yours.

5. **User-Friendly**: If you've ever found Google Analytics or Matomo confusing because of too many options, GoatCounter is a simpler and easier choice.

6. **Accessible**: It's designed to work well with screen readers and other assistive technology, making it more inclusive.

7. **Open Source**: GoatCounter is completely open source. You can see exactly how it works and even make changes to it. You can also host it yourself if you want.

8. **Control Your Data**: You're in charge of your data. You can export it anytime and stop using GoatCounter whenever you want.

## Getting started

Sign Up For [GoatCounter](https://www.goatcounter.com/signup)

![](/goatcounter.png "*Code* placeholder = your name/ sitename (make it memorable)" )

GoatCounter provides you with the following JavaScript code snippet:

``````js
<script data-goatcounter="https://YOURCODE.goatcounter.com/count"
    async src="//gc.zgo.at/count.js"></script>
``````
  - Replace YOURCODE with the name you entered above

Place the code in `layouts/partials/analytics.html` and comment out `googleAnalytics =` in `config.toml`.

## Push changes

Save all changes, commit, and let your site rebuild, and you should have data in `YOURCODE.goatcounter.com`, assuming your adblocker is not blocking GoatCounter (at`goatcounter.com` and/or `gc.zgo.at`) if you don’t see any page views. 
