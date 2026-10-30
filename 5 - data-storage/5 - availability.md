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

## NOTES

Primary replica architecture is where all writes go to a single primary server, and replicas pull from that primary to handle reads.

The main advantages are:

(1) improved performance for read-heavy applications, since the primary handles all writes without being slowed down by reads while replicas handle read operations,

and (2) less complexity since there's only one primary writing, avoiding concurrent write conflicts between nodes.

If the primary fails, a replica can take over.

However, replicas are not always consistent with the primary, so there's a risk of data loss if the primary fails between writes.

<hr />

The replicas are not always guaranteed to be consistent with the primary.

If the primary goes down in the middle of operation, the replicas will be almost consistent but not fully consistent, meaning there is still a risk of data loss.

The latency between writes to the primary and updates to replicas creates this consistency gap.

<hr />

### A traditional replication strategy and its trade-off.

In a transactional replication strategy, a write or update is not considered complete until all copies have the same data and all replicas have confirmed the write. 

This creates a highly consistent system. 

The trade-off is reduced performance and availability, as the system must wait for every database to acknowledge the write before responding, making it slower.

### The advantage of using snapshotting as a replication strategy.

Snapshotting provides several advantages: it's cheaper because it's not write-heavy (only occurring at periodic intervals), it provides better resiliency by preventing data corruption from spreading, and it guarantees a rollback point to the last known good state. 

Snapshots can also be taken at any desired frequency and are easier to distribute around the world since there's no time pressure.

