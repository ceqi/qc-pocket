---
layout: post
title:  "Hexagonal Architecture"
date:   2020-03-09 14:35:01 
categories: [Design]
tags: 
---

Dependencies go inside  

- Everything depends on domain, the domain does not depend on anything.  

Boundaries are isolated with interfaces

- ports and adapters
- domain defines ports, on which all kinds of adapters can be interchangeably connected 
