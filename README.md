I run LLM agents in production every day, at the scale of a small organization.

Most of what I build sits between the model and what ships: deterministic quality gates,
regression detection, cost ceilings, and recovery paths for long-running agent fleets.
The failures that cost me the most were never in the model. They were in the harness
around it.

I write those failures up two ways. As minimal runnable reproductions, and as
preregistered measurements.

## Reproducible failure labs

One file. No build tool. Run it, watch it break, then watch the same run with the fix.

- **[thread-pool-exhaustion-lab](https://github.com/renechoi/thread-pool-exhaustion-lab)**
  A slow dependency takes down endpoints that never touched it. Then the same run behind
  a bulkhead, so you can see what isolation buys and what it costs.
- **[duplicate-coupon-lab](https://github.com/renechoi/duplicate-coupon-lab)**
  A per-user limit sits right there in the code and the same person still gets two. Then
  the same run with the check and the registration fused into one operation.

## Measurement

- **[rdb-join-lab](https://github.com/renechoi/rdb-join-lab)**
  Benchmark harness for a preregistered study of ORM query patterns: JOIN vs N+1 vs
  IN-batch across RTT, result-set size and arrival rate. MySQL 8, Hibernate 6, tc netem, k6.

## Agent operations

- **[director-pattern](https://github.com/renechoi/director-pattern)**
  A layer that holds your stance between you and your products, and why that is not
  a dispatcher.
- **[ccpulse](https://github.com/renechoi/ccpulse)**
  Desktop tool that keeps a Claude Code token window aligned with a schedule.
  macOS, Linux, Windows.

## Research

Independent researcher. ORCID [0009-0004-4987-3897](https://orcid.org/0009-0004-4987-3897).

- *When Does N+1 Break a System? A Preregistered Measurement of Query-Pattern
  Performance-Degradation Boundaries.* First author.
  [10.5281/zenodo.21594741](https://doi.org/10.5281/zenodo.21594741)
- *When Do Agent Loops Mistake Stagnation for Progress? Self-Evaluation Bias and
  Externally Grounded Verification in Long-Running Autonomous LLM Agent Loops.*
  Co-authored.
  [10.5281/zenodo.21594735](https://doi.org/10.5281/zenodo.21594735)

---

Earlier writing and reading notes: [writes](writes.md) &middot; [reads](reads.md)
