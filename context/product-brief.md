# Satonomy — Product Brief

## What It Is
Bitcoin UTXO management API for companies/platforms. Non-custodial, dev-first. PSBT construction, fee optimization, Ordinals/Runes/Alkanes protection, transaction batching.

## Repos (ONLY THESE — never touch anything else)
- **Backend** (Rust/Axum): /Users/wiso/dev/satonomy/treasury-api — GitHub: estevanpedro/treasury-api
  - Deployed: Render (treasury-api-89vy.onrender.com, service ID srv-dam60u0u01pc73bk8vjg)
  - Single file: src/main.rs (~3100 lines, 39 API routes under /v1/)
  - DB: Turso/libsql (TURSO_DATABASE_URL, TURSO_AUTH_TOKEN NOT yet set on Render — BLOCKER)
  - GPG signing disabled: use `git -c commit.gpgsign=false commit`
  - Cold start: 10-30s on Render free tier
- **Frontend** (static HTML/CSS/JS): /Users/wiso/dev/satonomy/treasury-frontend — GitHub: estevanpedro/treasury-frontend
  - Deployed: Vercel (treasury-frontend-orpin.vercel.app)
  - Pages: index.html (landing), docs.html (API docs, 28 sections), dashboard.html
  - SDK dir exists but empty

## FOCUS
- Satonomy API dashboard, backend, frontend
- Offering what Satonomy App has as an API wallet
- Specifically UTXO management
- NOT the Satonomy Wallet or Satonomy App
- NOT satonomy.gitbook.io (that's for the App)

## Priorities (from competitive research)
1. MCP server (7 tools) + Xverse Agent Wallet partnership
2. TypeScript + Python SDKs
3. UTXO selection preview/simulation
4. UTXO state (AVAILABLE/FROZEN)
5. Consolidation advisor
6. WebSocket subscriptions

## Tech Stack
- Backend: Rust, Axum 0.7, Tokio, libsql/Turso, bcrypt, JWT, tower-http CORS
- Frontend: Static HTML/CSS/JS, Vercel
- Auth: JWT (24h expiry) + API keys (sk_live_*)
- Rate limiting: in-memory per-IP and per-user
- Plans: Builder (free, 5 keys), Pro ($49, 20 keys), Enterprise ($499, unlimited)
