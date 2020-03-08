---
layout: post
title:  "Distributed Databases Articles"
date:   2020-03-06 15:19:01 
categories: [Distributed Systems]
tags: 
---

These are the links I find useful for understanding Distributed Systems

[Distributed Systems in One Lesson by Tim Berglund](https://www.youtube.com/watch?v=Y6Ev8GIlbxc&t=1215s)  
- Storage
- Computation: MapReduce, Stream
- Messaging: Events


[Understanding database sharding](https://www.digitalocean.com/community/tutorials/understanding-database-sharding)  
- horizontal partitioning  
- break up one's data into two or more smaller chunks (logical shards), then logical shards are distributed across separate database nodes (physical shards)
- benefits: 
  - facilitate horizontal scaling
  - speed up query response time  
  - more reliable when facing outrage
- drawbacks:
  - db architecture complexity: unbalanced shards
  - difficult to return to unshared architecture
  - lack of native support, lack of docs  

Sharing techniques:
- key based: balanced shards, dynamically add or remove nodes is tricky
- range based: simple, unbalanced shards
- directory based: flexible, lookup table has impact to performance, single point of failure  

When to shard?
- large volume of data exceeds the capacity of a single db
- volume of read / write surpasses what a single node can handle


Before sharding, exhaust other options:  
- dedicated db server
- caching
- larger server
- more read replicas

Sharding can be a great solution to scale database horizontally, but adds a great deal of complexity and more potential failure points


[How Cassandra balances consistency, availability and performance](https://www.datastax.com/blog/2019/05/how-apache-cassandratm-balances-consistency-availability-and-performance)  

Distributed databases tend to be either "CP" or "AP" since network failure is inevitable (partition tolerance is needed) 

"AP" system (Availability, Partition Tolerance)

Replicas ensure data availability, but consistency can be tuned

High consistency helps ensure data accuracy, it impacts latency

Cassandra is configurable, can manage trade-offs between consistency, availability

[Brewer’s Conjecture and the Feasibility of Consistent, Available, Partition-Tolerant Web Services](http://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.67.6951&rep=rep1&type=pdf)

Consistency: atomic operations; exist a total order of all operations such that each operation looks as if it were completed at on single node; any read that begins after write completes must return that value.

Availability: every request must result in a response, even when severe network failures occur; puts no bound on how long the algorithm may run before terminating

Partition Tolerance: the network is allowed to lose arbitrarily many messages sent from one node to another.

