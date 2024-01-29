---
runme:
  id: 01HN7SXDPNGVED0W9J5E4JF25Y
  version: v2.2
---

# Scaling From Zero To Millions

## Walkthrough

1. Single server setup
2. Vertical/Horizontal Scaling + Load Balancer
3. Database Replication (Master-Slave Architecture)
4. Cache Layer (Redis) & CDN
5. Stateful Vs Stateless Architecture (NoSQL as session store for scalability)
6. Data centres with geoDNS
7. Message Queue for Decoupling
8. Logging, Metrics, Monitoring & Automation
9. Database Scaling (Vertical Vs. Horizontal/Sharding)
   - According to Amazon Relational Database Service (RDS), you can get a
     database server with 24 TB of RAM.
   - stackoverflow.com in 2013 had over 10 million monthly unique visitors, but
     it only had 1 master database.
   - Sharding is the practice of adding more servers. Each shard share the same
     schema, but have unique data. Requires a hash function on a
     sharding/partitioning key based on which the appropriate shard will be
     determined. It introduces further challenges:
     - Resharding: uneven sharding; consistent hashing to move data
     - Celebrity/Hotspot problem: excessive access to the same shard; imagine
       3 celebrities on the same shard.
     - Join and de-normalization: performing join on multiple sharded data is
       hard. De-normalize data into a single table.

Summary:
- It's an iterative process.
- Keep web tier stateless
- Build redundancy at every tier
- Cache data as much as you can
- Support multiple data centers
- Host static assets in CDN
- Scale your data tier by sharding
- Split tiers into individual services
- Monitor your system and use automation tools