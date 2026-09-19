# Recent product commits (captured 2026-09-18)

## treasury-api (git log --since='2 hours ago', HEAD `d4252a3`)

- `d4252a3` Speed up warm fee-estimate with full response cache and tighter read timeouts
- `c6132c2` docs: add CHANGELOG and CONTRIBUTING for developer onboarding
- `9585740` observability: log structured 4xx/5xx with method, path, status, latency
- `f7f8879` Nest API errors in Stripe-style error object with backward-compat message field
- `50c229b` Add Postman collection and English README for Phase 1 API
- `1ac83b8` chore: add Render /health uptime monitor script
- `1219887` chore: add Render blueprint and .env.example
- `1dd4091` Add Stripe-style error codes to API error responses
- `dbd8a46` Optimize /health to never block on database queries
- `538b38c` Optimize /health with cached DB check and no Turso rate-limit on ping

## treasury-api (prior capture)

- `d44c14f` ci: ping Render /health every 5 minutes to prevent cold starts
- `5ec11ba` security: RFC 9116 security.txt + CORS audit
- `187dd99` llms.txt + GET /llms.txt
- `ebe39f9` Builder free forever with RPS cap (overview quota 0)
- `9694883` Builder unlimited free with per-second cap
- `4ed03c2` Fix missing X-RateLimit headers
- `2bfe6c3` Fix rate limit key collision
- `2630bd6` persistent rate limiting via Turso (M5)
- `361f868` mempool upstream 502/503 JSON
- `e238239` health check Turso SELECT 1
- `b0e1f4e` tracing on live Bitcoin endpoints
- `3457ccb` CI regression suite
- `1eb7fd8` GitHub Actions fmt/clippy/tests
- `20406a6` bech32/base58check address validation (M6)
- `c68bfda` Phase 2 mempool stubs for PSBT tx fetching

## treasury-frontend (git log --since='2 hours ago', HEAD `e01eed0`)

- `e01eed0` Add 404 page polish and dashboard API offline handling
- `c099164` ci: add frontend workflow for links, tests, and console.error
- `e6f9848` Improve landing and dashboard performance and accessibility
- `45c8f70` docs: error codes reference and plan rate limits (req/s)
- `856c4f7` Polish dashboard layout, charts, keys, and activity log
- `a6d7262` docs(sdk): types reference, workflow example, align ApiErrorBody
- `46826d4` docs: add 30-second quickstart at top of docs.html
- `2781deb` Overhaul developer dashboard and remove all trial messaging
- `573ee3b` docs: end-to-end accuracy pass for live API examples
- `51d4c36` Fix mobile landing regressions, Bitcoin favicon, and OG meta
- `b08e95b` Polish landing trust signals and dashboard production states
- `d15dd44` docs(sdk): sprint 3 DX — sk_live auth, llms.txt links, publishConfig
- `0281ec9` docs: sidebar nav + Bitcoin API key auth labels
- `6bbc5d8` Update llms.txt to llmstxt.org spec with Phase 1 endpoint index

## treasury-frontend (prior capture)

- `0281ec9` docs: sidebar nav + Bitcoin API key auth labels
- `6bbc5d8` llms.txt Phase 1 endpoint index
- `0869b26` docs sprint 3 accuracy — badges, API key quickstart
- `676fc5e` restore Integrate in three steps
- `02a9a79` signup UX, plan copy, landing backgrounds
- `4470e2d` Builder unlimited free copy + 2 req/s
- `6c012e5` simplify landing + dark crypto theme
- `aea19cc` SEO meta + JSON-LD
- `9d66bf4` how-it-works three-step grid
- `dacf995` simplify landing + hidden SEO
- `29b2b2e` revert PSBT Coming Soon
- `1611bfe` Mark PSBT build Coming Soon (later reverted)
