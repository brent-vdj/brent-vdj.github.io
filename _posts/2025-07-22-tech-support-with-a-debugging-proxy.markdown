---
layout: post
title:  "Tech support with a debugging proxy"
date:   2025-07-22
categories: guide tech-support
---

## Introduction

While working in SaaS tech support, you'll often find yourself in situations having to reproduce an issue an end-user, or even a developer, is experiencing.

When it's a **front-end** issue, your browser's built-in devtools usually suffice, but once you start dealing with issues that involve multiple windows, such as SAML, a debugging proxy is extremely helpful.

Another common situation is **API** troubleshooting. When doing this, it's much easier to gather logs of your API requests and server responses using a debugging proxy.

Supporting a SaaS platform myself, a debugging proxy is one of the most valuable tools I've been using. There's many out there, but in this post, I'll be covering mitmproxy. It's a versatile tool that can be used for other purposes too.

## Installation

* Download mitmproxy from <https://mitmproxy.org>

* Run the installer and click through the installation

* Select "Start mitmproxy" at the end of the installation OR open CMD/PowerShell as Administrator and use `mitmproxy`

mitmproxy now listens on `http://localhost:8080` and you need to configure your browser to route all traffic through it.

* Manually configure your browser or computer to use `localhost` and port `8080` in its proxy settings, for both HTTP and HTTPS.
  * [Firefox - Connection settings in Firefox](https://support.mozilla.org/en-US/kb/connection-settings-firefox)

* Go to <http://mitm.it/>

If the proxy setup was succesful, this will show you a webpage with instructions on how to install the mitmproxy CA on your OS/browser combination.

* Browse to any HTTPS website, for example: <https://mitmproxy.org/>, and you should see the traffic appear:

![Image]({{site.url}}{{site.baseurl}}\images\2025-07-22-tech-support-with-a-debugging-proxy\35e69d0b-6a23-4603-94ec-ca71f44ff305.png)

## Using Postman

You can also set Postman to use the debugging proxy, so you can easily record and examine requests.

![Image]({{site.url}}{{site.baseurl}}\images\2025-07-22-tech-support-with-a-debugging-proxy\dc82ce12-f858-4bea-9ae5-caa12416f4ee.png)
