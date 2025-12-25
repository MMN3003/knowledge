- OLGP: Online General Purpose
- OLTP: Online Transaction Processing



OLTP designed for read-heavy or balanced workloads.
OLGP optimized from the ground up for write-heavy workloads.

TigerBeetle provides strong consistency guarantees without row locks

Horizontal scaling is a poor fit for OLTP:

- Most accounts cannot be neatly partitioned between shards.
- Transactions between accounts on different shards become more complex and slow.
- Row locks on hot accounts worsen when the transactions must execute across shards.

TigerBeetle uses a [single-core design](https://docs.tigerbeetle.com/concepts/performance#single-threaded-by-design) and unique performance optimizations to deliver high throughput. And this without the downsides of horizontal scaling.

TigerBeetle is designed to handle **1 million transactions per second**


OLTP and business transactions tend to record the same types of information:

- **Who**: which accounts are transacting?
- **What**: what type of asset or value is moving?
- **When**: when was the transaction initiated or when was it finalized?
- **Where**: where in the world did the transaction take place?
- **Why**: what type of transaction is this or why is it happening?
- **How Much**: what quantity of the asset or items was moved?



Money never appears from nowhere or disappears!!

TigerBeetle also supports [two-phase transfers](https://docs.tigerbeetle.com/coding/two-phase-transfers) out of the box, and can express complex atomic chains of transfers using [linked events](https://docs.tigerbeetle.com/coding/linked-events).
A two-phase transfer moves funds in stages:

1. Reserve funds ([pending](https://docs.tigerbeetle.com/coding/two-phase-transfers/#reserve-funds-pending-transfer))
2. Resolve funds ([post](https://docs.tigerbeetle.com/coding/two-phase-transfers/#post-pending-transfer), [void](https://docs.tigerbeetle.com/coding/two-phase-transfers/#void-pending-transfer), or [expire](https://docs.tigerbeetle.com/coding/two-phase-transfers/#expire-pending-transfer))

The name “two-phase transfer” is a reference to the [two-phase commit protocol for distributed transactions](https://en.wikipedia.org/wiki/Two-phase_commit_protocol).



continue on ## [Storage Fault Tolerance](https://docs.tigerbeetle.com/concepts/safety/#storage-fault-tolerance)
