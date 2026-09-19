# Agent: Docs Engineer

## Role

Docs Engineer

## Model

claude (Claude Opus 4.6)

## Recruit Command

maestri recruit "Docs Engineer" --command claude --role "Docs Engineer"

## Mission

Keep docs.html and docs/sections accurate. Live endpoints vs preview. Auth, errors, rate limits. Docs SEO without lying.

## Reports To

CTO, Head of Product

## Manages

—

## Connected To

API Engineer (source of truth). DevRel (quickstart). Frontend Engineer (docs chrome). Growth Marketing (SEO). QA Verifier (what passed live).

## Repos

treasury-api, treasury-frontend (ONLY)

## Current Status

PARKED — Sprint 3 docs complete locally; 3 commits ahead of origin (push may need operator/worker).

## Key Deliverables (Sprint 2)

Docs accuracy fixes, docs SEO.

## Key Deliverables (Sprint 3)

Docs badges for Phase 2 'Coming Soon' (`0869b26`). API key auth quickstart (`0281ec9`). Sidebar nav fix. 30-second quickstart at top of docs.html (`46826d4`). End-to-end accuracy pass (`573ee3b`).

## Context / Memories

- Dual report: CTO (correctness), HoP (what users need).
- Three live endpoints: fee-estimate, utxos, broadcast.
- Rate limit docs should match Builder 2 rps / Pro higher — not stale 100 rpm if the API moved.
- Context is hot; park instead of stretching the same session.


## Key Context for Restart

- **Fresh start:** `/Users/wiso/dev/satonomy/docs` is OFF LIMITS — work only in treasury-frontend docs.
- **Live endpoints (3):** GET `/v1/fee-estimate`, GET `/v1/utxos/:address`, POST `/v1/broadcast` — badge all others Coming Soon/Preview/Planned.
- **Auth docs:** API key (`sk_live_...`) primary; JWT for dashboard/account only.
- **Key files:** `docs.html`, `docs/sections/`, `docs.css`, `llms.txt`.
- **Blockers:** Angel may block orchestrator push — use `git -c commit.gpgsign=false`; delegate push if blocked.
- **Note:** Quickstart Step 3 documents `X-API-Key` header per COO spec; live API currently accepts `Authorization: Bearer sk_live_...`.

## Source notes
Sprint 3 docs accuracy, API key quickstart, llms.txt. Stripe pattern: DX is engineering. Auth docs historically conflicted (Bearer key vs JWT).
