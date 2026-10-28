# Relational database

Relational database really excels when you have data that is strictly related (They have a clear relationship to each other.) to each other's.

## ACID

First, atomicity: each transaction is all or nothing, either every operation succeeds or none do.

Second is consistent. Transactions always follow the rules set for the database.

Third is isolated, concurrent transactions do not interfere with each other's, do each run as if it were alone.

Fourth, durable: Once a transaction is safe, its changes are permanent.
