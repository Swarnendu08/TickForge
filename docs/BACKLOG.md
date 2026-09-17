# Timer Module — Prioritized Backlog

## P0 — unblock the first implementation

- [ ] Compare the separate timer thread/service model with building ISIS on top of the timer.
- [ ] Define timer states and legal transitions.
- [ ] Decide whether duration is fixed, adjustable, or both.
- [ ] Define pause/resume/reset/start semantics and completion behavior.
- [ ] Define callback/event delivery and error behavior.
- [ ] Select runtime/language and supported environments.
- [ ] Specify injectable clock/scheduler contract.
- [ ] Define owner identity, payload/correlator, expiry notification, and delivery guarantees.

## P1 — build confidence

- [ ] Implement a deterministic timer core.
- [ ] Add unit tests for normal progression and every public transition.
- [ ] Add tests for zero, negative, fractional, and very large durations.
- [ ] Add tests for repeated or invalid commands.
- [ ] Add a concise usage guide and API reference.

## P2 — release hardening

- [ ] Add CI for formatting, linting, and tests.
- [ ] Decide packaging/versioning strategy.
- [ ] Add changelog and compatibility policy.
- [ ] Document performance, drift, cleanup, and thread/event-loop constraints.
