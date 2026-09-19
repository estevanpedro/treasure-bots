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

PARKED — Sprint 3 shipped and pushed to origin (was 85.6% context pre-S3).

## Key Deliverables (Sprint 2)

`main.rs` modularization, `mempool.rs` (629 lines), auth fixes, rate limit fixes, security hardening, unlimited free Builder plan with RPS cap.

## Key Deliverables (Sprint 3)

Health endpoint optimization (`538b38c` — cached DB check, no rate-limit on ping). Stripe-quality error format refactor (`1dd4091`). Non-blocking cache reads. Push to origin complete.

## Context / Memories

- Builder is free forever. No trial_end for Builder. Cap is requests-per-second (`BUILDER_RPS = 2`).
- Pro still has a 14-day `trial_end`; do not copy that onto Builder.
- Monthly request quota for Builder is unlimited (overview `request_limit` 0).
- Context is hot — park rather than compact mid-task.


## Key Context for Restart

- **Fresh start:** Restore in a new terminal if context was hot; do not compact mid-task.
- **Recent commits:** `d4252a3` fee-estimate full response cache + tighter timeouts; `9585740` structured 4xx/5xx logs; `f7f8879` nested Stripe-style error + message compat; `dbd8a46` /health never blocks DB; `538b38c` health cache; `1dd4091` error JSON.
- **Live surface:** `src/main.rs`, `src/mempool.rs`, `src/auth.rs` — 3 Bitcoin endpoints on mainnet via mempool.space.
- **Plan flags:** Builder free forever, `BUILDER_RPS = 2`; Pro trial still exists — do not copy trial onto Builder.
- **Blockers:** None for API code; coordinate with Gateway before duplicating edge rate limits.
- **Repo:** `/Users/wiso/dev/satonomy/treasury-api` (primary), treasury-frontend only for llms.txt/docs cross-checks.

## Source notes
Mission-API: 39 routes, MCP, UTXO preview/state. GPG false.
Recent: RPS cap, Turso rate-limit table, address checksums, llms.txt, health ping, mempool stubs.
File ownership: treasury-api `src/` — no second agent edits same file.
