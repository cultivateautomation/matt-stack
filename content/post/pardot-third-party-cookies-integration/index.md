---
author: Matt Lincoln
title: Integrating Pardot with Cookie Consent Platforms
date: 2021-08-05
description: Pardot and third party cookie solutions overview
image: pardot-cookies.jpg
draft:
categories:
- pardot
- cookies
- gdpr
---

If you're reading this article, there's a chance you've been asked to integrate Pardot with a third-party cookie solution such as OneTrust, Cookiebot, Cookiehub, iubenda or Cookiefirst. Perhaps this is a proactive push to become compliant with GDPR or other privacy regulations, or you've been given a notice from a regulator that your cookie management isn't up to scratch. 

Either way, what you've likely found so far is that the Pardot documentation is barebones at best.

## Pardot Cookie Basics

- Pardot drops Cookies on a visitor's browser if they visit a page which includes either the Pardot tracking code OR a Pardot iFrame.
- [Multiple types of Cookies are used](https://help.salesforce.com/articleView?id=pardot_basics_cookies.htm&type=5), and they have different purposes
- These Cookies are enabled by default, however Pardot does include some out of the box functionality to prevent them from being set.

## Pardot's out of the box Visitor Tracking Opt-in Banner

Pardot wasn't very quick to help clients get ready for GDPR compliance. Fairly late in the run-up to the GDPR deadline, a Pardot banner option appeared in the platform. 

This banner can be set to display for all visitors to your website, or only for visitors from certain countries or regions.

The problem? This is not a viable solution if you're using a third party cookie management tool. You'd have two cookie banners - one from Pardot, and one from your cookie management platform!

## Pardot's "sneaky" cookies - the iframed web form

So the simple solution here is to just enable Pardot's website tracking code when a visitor opts in via your cookie preference tool, right?

Nope, it's not quite that simple. Check out the form below.

<iframe src="https://go.pardot.com/l/757603/2019-05-17/61j" width="100%" height="250" type="text/html" frameborder="0" allowTransparency="true" style="border: 0"></iframe>

There isn't any standalone Pardot tracking code installed on this page, yet Pardot is now dropping cookies, by virtue of the iframe above.

If you're using Pardot iFrames, this means that you could be noncompliant from a cookie perspective without realising.