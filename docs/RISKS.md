# Risks and Constraints

| Risk | Impact | Likelihood | Mitigation / trigger |
|---|---|---:|---|
| Runtime and consumer are unknown | High | High | Resolve target environment before implementation. |
| Timer drift or scheduler throttling | High | Medium | Define clock semantics; test elapsed-time behavior independently from tick frequency. |
| Ambiguous transition semantics | High | High | Write a state machine and examples before coding. |
| Invalid durations and repeated commands | Medium | High | Specify validation and idempotency/error policy; add boundary tests. |
| Resource leaks from timers/listeners | High | Medium | Define disposal/cleanup behavior and test it. |
| Scope expands into UI, persistence, or notifications | Medium | Medium | Keep those concerns out of the core milestone unless explicitly added to scope. |
| Premature coupling to ISIS reduces reuse | High | Medium | Keep the architecture comparison exploratory and define owner-neutral payload/correlator semantics. |
| Dedicated-thread overhead is unnecessary or causes scheduling friction | High | Medium | Benchmark a separate service/thread against a shared scheduler once requirements are known. |
| Expiry notification delivery is ambiguous across owners | High | Medium | Specify ownership, ordering, unavailable-owner behavior, and delivery guarantees in the contract. |

## Constraints currently observed

- No source, tests, package metadata, documentation, or commit history are present.
- No verified runtime, dependency, CI, or release constraints are present.
