---
layout: post
title:  "Consistent Hashing"
date:   2020-03-22 12:49:01 
categories: 
tags: 
---

Concept from paper [Consistent hashing and random trees](https://www.akamai.com/us/en/multimedia/documents/technical-publication/consistent-hashing-and-random-trees-distributed-caching-protocols-for-relieving-hot-spots-on-the-world-wide-web-technical-publication.pdf)

Consistent hashing solves the problem that caching in a non-fixed collection of servers where caching is through hashing.  

Cache / Hash table becomes so big that one server can't fit, so how to store it?

Distributed Hashing is to distribute the hash table to multiple servers to avoid memory limitation of one server.

Q: which server to store a key?  
A: server = hash_func(key) modulo
N where N is number of servers.

Problem for this approach is that when rehashing, most keys are rehashed resulting in cache miss and performance hit.  

Consistent hashing is a distributed hashing mechanism that's not depended on number of servers.

Keys and servers are assigned on a `Hash Ring`, a virtual circle. 

Virtual nodes to balance the load.

