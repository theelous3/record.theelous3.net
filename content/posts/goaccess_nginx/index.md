---
title: "Stupid goaccess reverse proxy websocket port trick"
date: 2025-12-09T14:15:40Z
draft: false
tags: [code, servers, goaccess, nginx]
categories: []
author: ""
showToc: true
TocOpen: false
hidemeta: false
comments: false
description: ""
canonicalURL: ""
disableShare: false
disableHLJS: false
hideSummary: false
searchHidden: false
ShowReadingTime: true
ShowBreadCrumbs: true
ShowPostNavLinks: true
cover:
  image: "x.png"
  hiddenInSingle: false
---

Setting up live goaccess behind a reverse proxy has an arcane and stupid trick.

In order to get your browser to stop trying to connect your websocket to `wss://whatever.com:7890/ws` where port `7890` is both nonsense (your reverse proxy is not listening there) and insecure (your browser doesn't want to deal with this port), you must define your config to explicitly use the port it should already be using, `80` or `443` depending on ws or wss.

The `--port` param is the port at which goaccess is its self available on your localhost. If it is unset in your `--ws-url` it doesn't use a sensible default, it uses the value from `--port` again.

This way your browser will hit your reverse proxy at the correct `443`, and your proxy will proxy to `7890` or wherever goaccess lives.
