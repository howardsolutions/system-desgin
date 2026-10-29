# DB SCALING

## PARTITIONING

Sharding is a type of partitioning. That is why it's going to get a little bit confusing when it comes to differentiate between these two terminologies.

Partitioning just means you are slicing your data on some field.

For instance, that we have a VERY LARGE database of users, which is a giant database, and we're going to pick a field. Let's say we're going to pick the user ID and then we're going to go ahead and then slice it in half.

# HERE IS THE SECRET: PARTITIONING HAPPENS ON THE SAME DATABASE

It is not on the second database, it is on the same database.

As a result, we could speed up our queries `substantially` by just doing that.

## SHARDING

SHARDING is also trying to slice your data on some arbitrary key called `a sharp key` to make INCREASE PERFORMANCE

# But sharding implies you are `doing it over a different machine`.

And just by doing these two techniques, it's good to dramatically increase your query performance.

On the first time when you hit the limit on the database, you should always think of partitioning because it's easier to do at first because it's all on the same database.

WE always have to think about doing the simplest thing first. And when we hit the limit of partitioning, that is when we think about doing the sharding.

That is how we scale the relational database horizontally, but still maintaining the ACID compliance.

# FOR NON-RELATIONAL DATABASE

The sharding happens automatically. For instance, MongoDB is just built to do that. It scales horizontally automatically.

It's cool

## You really only have to think about this when you talk about Relational database.

That is why non-relational is kind of cooler. It automatically horizontally scales where you don't have to think about it.

# SUMMARIZES

## PARTIONING

Your data fits on one server, you need transactional guarantees, queries that span multiple tables.

Partitioning is slicing data on the same machine/database, while sharding is slicing data across different machines/databases. Both involve dividing data based on some key to increase performance, but sharding implies distribution across multiple servers.

Partitioning is done first because it's simpler - it doesn't require adding another database or managing additional servers.

You're just slicing the data differently within the same database to make queries faster.

Only after hitting the limits of partitioning would you move to sharding, which adds complexity by distributing data across multiple machines.

## SHARDING

A shard key is an arbitrary field used to determine how data is distributed across different sharded databases. It's critical to choose it carefully because if chosen incorrectly, data may not be evenly distributed, leading to `some database clusters being overloaded while others are underutilized.`

For example, sharding by first name assumes names are evenly distributed across the alphabet, which may not be true.

### There is a potential performance drawback when using sharding for database with complex query.

When queries need to span multiple tables that are distributed across different sharded databases, the performance will be slower than querying a single large machine.

This is because the query must reach across multiple databases, which adds network overhead and complexity compared to accessing all data on one server.
