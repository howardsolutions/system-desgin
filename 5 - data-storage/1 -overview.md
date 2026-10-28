# Data storage

"At the end of the day, most of what you do is READING FROM and WRITING TO a DATABASE"

- use the simplest solution for DB, we could always scale up later

## DIMENSIONS

structured vs unstructrued

persistent vs ephemeral

read-optimized vs write-optimized

consistency vs availability

## Data Storage

### Relational

SQL, structured data with relationships
enforced schema
ACID transactions

### Non-Relational

NoSQL, semi or unstructured data
flexible
horizontal scale

# MORE NOTES

Write-heavy applications include logging systems, metric collection, and eventing systems. 
Read-heavy applications include npm (where most users download packages), social media (where users mostly scroll), and data warehouses. Most applications are read-heavy with ratios ranging from 10:1 to 1000:1 reads to writes.

