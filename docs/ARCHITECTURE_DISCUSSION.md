# Timer Module — Architecture Discussion

## Purpose

The Timer Module is intended to be a reusable, lightweight all-rounder that can support game-development modules, server-operation modules, notification managers, and networking protocol managers.

Its primary non-functional goal is very low processor overhead with smooth, predictable operation. Timer requests should carry an owner-defined payload or correlator so the owner can identify and interpret the expiry without the timer module needing domain-specific knowledge.

## Exploratory approaches

### Model A — Separate timer thread or service

Run the Timer Module as a separate timer thread/service within the application. Owner modules communicate with it to start, modify, or delete timers. Each request includes an owner-defined payload/correlator. When a timer expires, the timer service notifies the owner and returns that payload/correlator.

Example: ISIS starts a hello timer with an ISIS-owned correlator; on expiry, ISIS receives the correlator back and interprets it.

### Model B — Build ISIS on top of the timer

Build ISIS directly on top of the Timer Module if that layering is technically viable. This may provide a concrete first consumer and allow the timer abstraction to be shaped around real protocol needs, but the implications for reuse, coupling, and ownership remain open.

## Pros and cons placeholder

Evaluate both models later against processor overhead, scheduling smoothness, API simplicity, ownership and lifecycle, isolation, testability, scalability across many owners, and coupling to ISIS. No approach is selected yet.

## Open questions

- What runtime, threading, event-loop, and deployment model must be supported?
- Is a dedicated thread necessary, or can an efficient shared scheduler satisfy the overhead and smoothness goals?
- What timer operations are required: start, modify, delete, pause, resume, and query?
- What are the delivery guarantees, ordering rules, and behavior when an owner is unavailable?
- Is the payload copied, referenced, serialized, or otherwise constrained?
- How are timer identity, ownership, cancellation races, shutdown, and cleanup represented?
- What precision, drift tolerance, timer volume, and latency bounds are required?
- How should recurring timers and missed or delayed expiries behave?
- What ISIS-specific needs would risk leaking into the reusable core?
