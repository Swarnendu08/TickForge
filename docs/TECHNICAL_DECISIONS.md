# Technical Decisions

## Decision log

### TD-001 — No implementation assumptions yet

- **Status:** Open
- **Context:** The repository has no source files, commits, runtime declaration, or consumer documentation.
- **Decision:** Keep the initial work contract-first. Do not select libraries or add product code until the target runtime and timer semantics are explicit.
- **Consequence:** Discovery is the current critical path; the first deliverable is a contract and test plan.

### TD-002 — Prefer deterministic time in tests

- **Status:** Proposed
- **Decision:** Use an injectable clock/scheduler abstraction rather than sleeping against real time in unit tests.
- **Rationale:** This reduces flakiness and makes pause, resume, completion, and boundary behavior reproducible.

### TD-003 — Architecture remains exploratory

- **Status:** Open
- **Context:** The module should serve multiple owner domains, including ISIS, while keeping processor overhead very low and operation smooth.
- **Options:** Use a separate timer thread/service that accepts owner requests, or build ISIS on top of the timer module if technically viable.
- **Decision:** No architecture is selected yet. Evaluate both options after clarifying runtime, scheduling, ownership, payload/correlator, delivery, and performance requirements.
- **Reference:** See `ARCHITECTURE_DISCUSSION.md`.
