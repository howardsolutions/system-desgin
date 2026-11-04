# Scaling Notes

## When scaling a to-do application that is experiencing slow reads due to database limitations, what is the first and easiest optimization to implement before considering database migration

Add a cache layer (such as Redis) in front of the database.
This is particularly effective for `read-heavy applications` and can `significantly increase capacity` without requiring expensive database migrations or architectural changes.

## What is the recommended sequence of scaling strategies for a relational database as traffic increases from thousands to millions of users?

The sequence is:

1. Add caching (e.g., Redis) to handle read-heavy load,

2. Vertical scaling (scale up the database instance to a larger size)

3. Partitioning within the database

4. Sharding with a load balancer to distribute across multiple databases (adding a cache for each shard)

5. Read replicas to separate read and write operations. Each step should be implemented only `when the previous approach reaches its limits.`

## Why is database migration (such as switching from a relational database to NoSQL) typically considered the last resort when scaling an application?

Database migrations are expensive, involve potential downtime unless done very carefully, and require specialized database administrators.

It's better to exhaust other scaling strategies first, such as caching, vertical scaling, partitioning, sharding, and read replicas.

## When implementing database sharding for a scaled application, what additional infrastructure components become necessary?

A load balancer is needed to route requests to the correct shard, and typically a cache should be placed in front of each sharded database.

This increases system complexity with more components to manage and monitor.

## What is an important consideration when implementing read replicas after sharding a database?

When you replicate after sharding, you need to replicate each sharded database individually. 

This means the replication strategy must be applied across all shards, adding to the complexity and resource requirements of the system.

