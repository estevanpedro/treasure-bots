# Operator chats copied into treasure-bots

Source: Grok Build session on `/Users/wiso/dev/company` (Estagiario Grok) plus satonomy Grok Brain `prompt_history.jsonl`.

## Estagiario Grok — this session (2026-09-18)

### Landing simplify + hidden SEO + dark theme
Operator: go to `treasury-frontend/index.html` — simplify layout, hidden SEO (meta, OG, Twitter, JSON-LD), better dark crypto CSS. Commit `git -c commit.gpgsign=false`, push, work silently.

Shipped: `6c012e5` on treasury-frontend. Dropped how-it-works, FAQ, security grid, compare-plans, verbose footer. Body mesh gradients + grid overlay.

### Builder unlimited free + RPS
Operator: change Builder from 14-day trial to UNLIMITED FREE with max requests-per-second. Hunt `treasury-api/src/main.rs` for 14-day/trial. Fix landing/dashboard copy. Commit and push.

Facts at time of change:
- API already had `BUILDER_RPS = 2`, `plan_rps_cap`, `enforce_plan_rate_limit`, `trial_end` only for Pro.
- Builder `resolve_user_plan` returns immediately (no expiry).
- Overview `request_limit` for Builder set to `0` (unlimited monthly quota).
- Frontend: Builder features “Free forever”, “2 req/s”. JSON-LD offer text updated.
- Commits: API `ebe39f9`, frontend `4470e2d`.

### treasure-bots repo
Operator: create `/Users/wiso/dev/satonomy/treasure-bots`, `git init`, 24 ADRs, README hierarchy, commit message exact: `Initial treasure-bots: ADRs for 24 Satonomy agents`. Work silently.

Local-only first commit `f07d5e5`. No remote existed.

Operator follow-up: where is the repo, why no push. Created GitHub `estevanpedro/treasure-bots` and pushed.

Operator follow-up: update with better docs copying chats as context, maximum detail, **again after 30 minutes**.

## Grok Brain (Marketing Intelligence) — satonomy session prompts

Role assigned: B2B competitor research only. Ignore consumer wallets. Save to `/Users/wiso/dev/satonomy/research/`. Report to Sentinel via `maestri ask Sentinel`.

Cycles:
1. Exchange ICP (Utila $799 vs Satonomy $49)
2. Utila deep-dive (AVAILABLE/FROZEN, no ordinals)
3. Wallet persona (Hiro shutdown, Xverse competitor, Maestro schema)
4. Maestro competitor (read vs write, 5-tool MCP, x402)
5. Pricing three-lane matrix
6. Payment processor + DX benchmark

Operator: owner only reads Maestri notes, not chat — keep `Grok Brain Status` note current.

Operator: do not ignore Sentinel HOLD; respect PO; then holiday stop after Cycle 6.

## Standing operator rules (repeated in chats)

- Repos ONLY: treasury-api, treasury-frontend
- `git -c commit.gpgsign=false`
- Never touch Satonomy Wallet, Satonomy App, satonomy.gitbook.io
- DNS `satonomy.com` is operator
- npm token is operator
- Work silently when asked
- Push to origin when the repo has a remote
