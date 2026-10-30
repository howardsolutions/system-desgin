# Availability: primary, replica, and snapshots.

What happens when things go wrong?

## Replication

Making copies of your data across multiple servers or locations 

increases fault tolerance 

and increases read performance. 

## Primary / Replica

1. All write go to the primary server.

2. The replicas copy data from primary and handle READ requests. 

3. If the primary fails, a replica can take over.

## Primary / Primary.

Multiple server accept write and reads, data is synchronized between all servers.

## Peer to peer.

Every server can read and write; changes are shared with all other servers.

## STRATEGIES

- Transactional, Snapshot, and Merge.
