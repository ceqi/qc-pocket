---
layout: post
title:  "Consistent Hashing"
date:   2020-03-22 12:49:01 
categories: 
tags: 
---

## Consistent Hashing

How to store a big hash table that's not fit into one server?

Distributed Hashing is to distribute the hash table to multiple servers to avoid memory limitation of one server.

Q: which server to store a key?  
A: server = hash_func(key) modulo
N where N is number of servers.

Problem for this approach is that when rehashing, most keys are rehashed resulting in cache miss and performance hit.  

Consistent hashing is a distributed hashing mechanism that's not depended on number of servers.

Keys and servers are assigned on a `Hash Ring`, a virtual circle. 

Virtual nodes to balance the load.

