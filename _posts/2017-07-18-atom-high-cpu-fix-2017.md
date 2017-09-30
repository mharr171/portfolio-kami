---
layout: post
title: Atom — High CPU Usage Fix (2017)
---
Today my mentor recommended that I give Atom another shot. I had previously tried Atom on my own and loved it, but it quickly started to blow up my CPU, often hitting 90%+. I had searched for a fix before, but no answers turned up. But today, that changed.

Just recently an answer to my prayers was posted
[here](https://github.com/atom/atom/issues/9086). To fix the high CPU usage
problem, simply press cmd+shift+p and type ‘package’ to get to the package
management screen. Search for ‘git’ and disable both git-diff and github.
