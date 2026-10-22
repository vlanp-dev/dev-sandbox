# AI Agent Controller Dev Sandbox

This repository is the blank, disposable development sandbox created and owned by
the AI Agent Controller. It is intentionally minimal and exists only to be
written to, changed, and reviewed by the Controller.

## Purpose

The sole purpose of this repository is to exercise Controller WorkItems
end-to-end: a WorkItem is planned, implemented, reviewed, and merged here so that
the Controller's own process can be validated against a low-risk target.

It is useful to keep the following in mind:

- This repository is **not** a mirror of production and **not** a mirror of any
  specific external environment.
- It contains **no production code** and **no secrets**. Nothing here is
  deployed, and nothing here should be treated as a source of truth for a real
  system.
- Content in this repository is expected to change or be discarded as part of
  exercising the Controller.

## How this repository is validated

Validation happens outside this repository, through the Controller:

1. **Planning** — the WorkItem is turned into a technical design and a bounded
   engineering plan.
2. **Implementation** — an implementation agent makes the smallest change that
   satisfies the assigned plan task.
3. **Required reviews** — independent reviewers inspect the candidate change,
   such as architecture, security, and DevOps review, depending on the
   WorkItem.
4. **QA** — the candidate is checked against the WorkItem's acceptance criteria.
5. **Controlled commits** — the Controller, not the implementation agent,
   creates the commit for a reviewed candidate.
6. **Provider checks** — the configured provider and model are verified as part
   of the run.
7. **Merge gate** — the change is only merged once the preceding steps are
   satisfied.

In addition, the running dev stack exposes:

- `GET /health` — a liveness check confirming the application process is up.
- `GET /ready` — a readiness check confirming the application is able to serve
  traffic.

## Current validation status

There is currently **no test suite**, **no CI workflow**, and **no validation
scripts** in this repository. Repository-level tests and CI workflows do not
exist yet. Validation is limited to the Controller pipeline described above and
to the dev stack's `/health` and `/ready` checks. No automated repository checks
should be assumed.

## Scope

Controller-specific details — configuration, deployment, infrastructure, and
operations — are out of scope for this README. They are deferred to the AI Agent
Controller deploy documentation, which is the authoritative source for those
topics and is not reproduced here.
