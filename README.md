Staff engineer building ingestion systems that move billions of events daily.

## Muriel Barrows

I design and operate data ingestion pipelines that turn raw telemetry into queryable truth. I own the full lifecycle: schema evolution, partition strategy, and the retry logic that keeps backpressure from becoming a fire drill. I trade latency for durability where the contract demands it, and I keep the critical path boring.

### 🛠 Tech & Infrastructure

**Core**: `Python`, `asyncio`, `FastAPI`, `pydantic`

**Data**: `Kafka`, `PostgreSQL`, `ClickHouse`, `Parquet`

**Infra**: `Docker`, `Kubernetes`, `Terraform`

**Tooling**: `pytest`, `ruff`, `mypy`, `GitHub Actions`

### ⚙️ Engineering Areas

- Schema migration across partitioned tables with zero-downtime backfill
- Idempotent consumer design for exactly-once semantics on at-least-once delivery
- Query optimization on wide Parquet files with predicate pushdown and column pruning
- Capacity planning for Kafka clusters under uneven partition load

### 🔭 Current Focus

- Reducing tail latency in the ingestion path without adding a second queue hop
- Shrinking the gap between schema validation and storage-time enforcement
- Automating partition rebalancing for skewed keys that outgrow their hot shard
- Moving from manual runbooks to self-healing retries with exponential backoff and jitter

### 📌 Engineering Notes

- Tests that mock the network are fiction; integration tests with real queues and databases are the only ones that count.
- Migrations should be additive, reversible, and small; never rewrite a table in place while traffic is flowing.
- Retries are not a substitute for idempotency; every consumer must be able to replay a message without side effects.
- If a deployment isn't observable through traces and metrics within five minutes, it's not ready to ship.

### 🧭 How I Work

- Prefer boring, well-understood technology over clever abstractions that no one else can debug.
- Write code that fails loudly in development and degrades gracefully in production.
- Measure first, then optimize; the fastest query is the one you never run.

*Latency is a budget, not a goal.*