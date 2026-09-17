# Timer Module — Project Plan

## Purpose

This repository is intended to become the home for a timer module, but it currently contains no product source, documentation, or committed history. The immediate objective is to establish a small, testable baseline before implementation expands.

## Current baseline

- Repository: Git repository on `main`; no commits yet.
- Implementation: none found.
- Documentation: none found.
- Tooling and runtime constraints: not yet specified.

## Outcomes

1. Define the timer behavior and public interface.
2. Implement a minimal reliable timer core.
3. Add tests for time progression, pause/resume, reset, completion, and edge cases.
4. Document integration and operational constraints.

## Milestones

| Milestone | Exit criteria | Status |
|---|---|---|
| M0 — Discovery | Scope, API assumptions, and constraints recorded | In progress |
| M1 — Contract | Timer states, events, inputs, and clock strategy agreed | Not started |
| M2 — Core | Minimal implementation passes deterministic tests | Not started |
| M3 — Integration | Consumer-facing usage documented and verified | Not started |
| M4 — Release readiness | CI, versioning, changelog, and known risks addressed | Not started |

## Working assumptions

- Time should be driven by an injectable clock or scheduler so tests do not depend on wall-clock sleeps.
- The timer should expose explicit state transitions rather than requiring consumers to infer state from elapsed time.
- The module should remain reusable across game, server, notification, and networking owners.
- Timer requests should support an owner-defined payload/correlator returned with expiry notifications.
- Product-specific UI, persistence, notifications, and concurrency policy are out of scope until the contract is defined.

## Architecture direction under discussion

Two exploratory models are recorded in [ARCHITECTURE_DISCUSSION.md](ARCHITECTURE_DISCUSSION.md): a separate timer thread/service, or building ISIS on top of the timer. The choice remains open pending technical evaluation, especially around processor overhead, smoothness, coupling, ownership, and delivery semantics.

## Next smallest actionable task

Write `docs/timer-contract.md` with the initial state machine and API questions, then review it before choosing a runtime or implementation shape.
