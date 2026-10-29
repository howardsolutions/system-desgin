# NON Relational Database.

- Document stores data as flexible structures, documents like JSON. (MongoDB)

Document stores are a good choice when you need to store data that doesn't have a strict schema, may change over time, or doesn't require every document to have the same fields. 

They're ideal for catalogs or collections where the structure might vary between items, as they store data in JSON-like blobs that allow for flexible schemas.

- Key-value stores data as simple pairs of unique keys and their values. (Redis)

Key-value stores are very fast because there is no lookup required - the data is already indexed by the key. Since there are only two things being stored (the key and the value), reads are extremely fast. This makes them ideal for use cases like caching and session storage where fast lookups are critical.

- Column organizes data into columns instead of rows for fast retrieval of similar data. (Cassandra)

Column databases are optimized for searching and situations where you don't need a strict structure.

They store similar data together in columns (like all names in a name column), making queries for specific fields very fast. They can also reduce storage through encoding when there are repeated values, as the repetition can be represented more efficiently.

- Graph stores data as nodes and relationships, making it easy to represent and query connections. (Neo4j?)

Graph databases are designed to map relationships and connections between entities.

Common use cases include social networks (mapping connections between users) and fraud detection (identifying patterns and relationships between transactions to detect fraudulent activity).

They excel at problems that require analyzing complex relationships and connections.
