# Relational database

Relational database really excels when you have data that is strictly related (They have a clear relationship to each other.) to each other's.

## ACID compliance

First, atomicity: each transaction is all or nothing, either every operation succeeds or none do.

for example, if a transaction requires a read and a write and 2 reads, all of those operations must work or the whole transaction fails.

Second is consistent. Transactions always follow the rules set for the database.

Third is isolated, concurrent transactions do not interfere with each other's, do each run as if it were alone.

Fourth, durable: Once a transaction is safe, its changes are permanent.

# NOTES:

Relational databases are better suited for strict, consistent data storage schemes.

They provide stronger guarantees about data integrity and consistency, though the cost of fixing an incorrect schema is very expensive if discovered later.

#s# Differences between horizontal and vertical scaling in the context of a database.

Horizontal scaling is like adding multiple ovens, while vertical scaling is like getting a bigger oven.

Relational databases typically scale vertically (getting bigger), and do not scale horizontally automatically like non-relational databases.

While you can horizontally scale a relational database by slicing the data and creating additional servers, this is complex and expensive because of the transactional nature - you have to manually decide how to partition the data and ensure consistency across servers to avoid conflicts like two people writing to different databases for the same document.

## Relational databases excel at complex queries compared to non-relational databases.

Relational databases can perform complex queries quickly because the data is structured with clear relationships and uses indexing. Through indexing (typically B-tree structures), the database knows exactly where data is located and which column it's in, allowing for direct lookup rather than sequential scanning. This enables very fast extraction of data. In contrast, non-relational databases with unstructured data must search field by field, making queries slower.

## Denormalization in the context of non-relational database.

Denormalization is the practice of duplicating data rather than spreading it across multiple relations (the opposite of normalization). 

In non-relational databases like MongoDB, denormalization is often used to optimize read performance by putting everything in one document, though this must be balanced against document size limits (such as MongoDB's 16 megabyte limit)..
