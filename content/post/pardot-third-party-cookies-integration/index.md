---
author: Matt Lincoln
title: Integrating Pardot with Cookie Consent Platforms
date: 2021-01-02
description: Pardot and third party cookie solutions overview
image: pardot-cookies.jpg
draft: true
categories:
- pardot
- cookies
- test
---

If you're reading this article, there's a chance you've been asked to integrate Pardot with a third-party cookie solution such as OneTrust, Cookiebot, Cookiehub, iubenda or Cookiefirst. Perhaps this is a proactive push to become compliant with GDPR or other privacy regulations, or you've been given a notice from a regulator that your cookie management isn't up to scratch. 

Either way, what you've likely found so far is that the Pardot documentation is barebones at best.

## Pardot Cookie Basics

- Pardot drops Cookies on a visitor's browser if they visit a page which includes either the Pardot tracking code OR a Pardot iFrame.
- [Multiple types of Cookies are used](https://help.salesforce.com/articleView?id=pardot_basics_cookies.htm&type=5), and they have different purposes
- These Cookies are enabled by default, however Pardot does include some out of the box functionality to prevent them from being set.

## Pardot's out of the box Visitor Tracking Opt-in Banner

Pardot wasn't very quick to help clients get ready for GDPR compliance. Fairly late in the run-up to the GDPR deadline, a Pardot banner option appeared in the platform



Mathematical notation in a Hugo project can be enabled by using third party JavaScript libraries.


Test In this example we will be using [KaTeX](https://katex.org/)

- Create a partial under `/layouts/partials/math.html`
- Within this partial reference the [Auto-render Extension](https://katex.org/docs/autorender.html) or host these scripts locally.
- Include the partial in your templates like so:  

```bash
{{ if or .Params.math .Site.Params.math }}
{{ partial "math.html" . }}
{{ end }}
```

- To enable KaTex globally set the parameter `math` to `true` in a project's configuration
- To enable KaTex on a per page basis include the parameter `math: true` in content files

**Note:** Use the online reference of [Supported TeX Functions](https://katex.org/docs/supported.html)

{{< math.inline >}}
{{ if or .Page.Params.math .Site.Params.math }}
<!-- KaTeX -->
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/katex@0.11.1/dist/katex.min.css" integrity="sha384-zB1R0rpPzHqg7Kpt0Aljp8JPLqbXI3bhnPWROx27a9N0Ll6ZP/+DiW/UqRcLbRjq" crossorigin="anonymous">
<script defer src="https://cdn.jsdelivr.net/npm/katex@0.11.1/dist/katex.min.js" integrity="sha384-y23I5Q6l+B6vatafAwxRu/0oK/79VlbSz7Q9aiSZUvyWYIYsd+qj+o24G5ZU2zJz" crossorigin="anonymous"></script>
<script defer src="https://cdn.jsdelivr.net/npm/katex@0.11.1/dist/contrib/auto-render.min.js" integrity="sha384-kWPLUVMOks5AQFrykwIup5lo0m3iMkkHrD0uJ4H5cjeGihAutqP0yW0J6dpFiVkI" crossorigin="anonymous" onload="renderMathInElement(document.body);"></script>
{{ end }}
{{</ math.inline >}}

### Examples

{{< math.inline >}}
<p>
Inline math: \(\varphi = \dfrac{1+\sqrt5}{2}= 1.6180339887…\)
</p>
{{</ math.inline >}}

Block math:
$$
 \varphi = 1+\frac{1} {1+\frac{1} {1+\frac{1} {1+\cdots} } } 
$$
