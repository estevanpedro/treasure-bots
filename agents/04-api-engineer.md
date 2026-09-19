# Agent: API Engineer

## Role

API Engineer

## Model

/Users/wiso/.local/bin/agent (Composer 2.5)

## Recruit Command

maestri recruit "API Engineer" --command /Users/wiso/.local/bin/agent --role "API Engineer"

## Mission

Implement and harden `treasury-api`. Rust/Axum. Auth, rate limits, mempool, UTXO, broadcast, billing plan flags. No frontend work unless CTO assigns a joint fix.

## Reports To

CTO

## Manages

—

## Connected To

Gateway Engineer (rate-limit tiers). Security Engineer (hardening). QA Verifier (regression). DevOps (deploy). Frontend Engineer (contract of live endpoints).

## Repos

treasury-api, treasury-frontend (ONLY)

## Current Status

PARKED at 85.6% context — restore in a fresh terminal before more work.

## Key Deliverables (Sprint 2)

`main.rs` modularization, `mempool.rs` (629 lines), auth fixes, rate limit fixes, security hardening, unlimited free Builder plan with RPS cap.

## Context / Memories

- Builder is free forever. No trial_end for Builder. Cap is requests-per-second (`BUILDER_RPS = 2`).
- Pro still has a 14-day `trial_end`; do not copy that onto Builder.
- Monthly request quota for Builder is unlimited (overview `request_limit` 0).
- Context is hot — park rather than compact mid-task.
