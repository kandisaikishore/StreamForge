# Scalability and capacity plan

- Bound ingestion payload sizes and request concurrency.
- Separate interactive API traffic from long-running stream processing where supported.
- Use durable offsets/checkpoints and idempotent consumers to recover after restarts.
- Apply backpressure rather than buffering unbounded data in memory.
- Partition or batch workloads only after measuring volume and ordering requirements.
- Set connection/request timeouts and bounded retries for upstream/downstream systems.
- Track ingest lag, throughput, p95/p99 processing latency, queue depth, retry rate, and consumer failures.
- Test burst traffic, malformed events, duplicate delivery, consumer restart, and dependency outage.

## Release gates
- [ ] Replay and checkpoint recovery are tested.
- [ ] Backpressure and bounded memory are validated.
- [ ] Event ordering guarantees are documented.
- [ ] Load-test assumptions and results are recorded.

No production throughput target is asserted.
