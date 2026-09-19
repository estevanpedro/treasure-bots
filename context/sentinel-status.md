# SENTINEL (PO) STATUS
> Updated: 2026-09-18 (Cycle 6 audit complete)
> Role: Product Owner — audit everything, prioritize work, ensure quality
> Terminal: Background job (no MAESTRI_SOCKET — cannot write maestri notes directly)

## COMPLETED THIS SESSION

### Backend (treasury-api-27) — 7 commits, all verified clean
- `e02c619` PSBT preview + consolidation advisor stub endpoints
- `9fe7955` Rate limiting on 14 unprotected endpoints
- `dbfc756` UTXO state AVAILABLE/FROZEN + asset fields
- `c4e1f44` Health endpoint rate limiting
- `d6ef6e3` Metaprotocol arrays (inscriptions[], runes[], alkanes[]) + filter params + postage/dummy
- `aa0b730` MCP server config (7 tools)
- `e1fb91d` MCP trimmed to 5 construction-only tools

### Frontend — 10+ commits verified
- `e331afc` Gap positioning (3-column: Free RPC → Satonomy → MPC Custody)
- `a878d68` Hiro migration card for displaced Ordinals/Runes API users
- `bece240` Endpoint count 33→35 + MPC custody FAQ fix
- `d23b35e` Docs: PSBT preview, consolidation advice, UTXO state fields
- vs-custody table, vs-indexers table, ROI calculator, security polish, dark-mode fixes

### Research Audited (6 cycles from Grok Brain + Analyst)
- Cycle 1: Exchange persona ICP (Utila $799 vs us $49, non-custodial wedge)
- Cycle 2: Utila deep-dive (AVAILABLE/FROZEN, predictive preview, BTC fungible — no ordinals)
- Cycle 3: Wallet persona (Hiro shutdown, Xverse-as-competitor, Maestro schema, postage/dummy)
- Cycle 4: Maestro competitor (read vs write line, 5-tool MCP, x402 strategy)
- Cycle 5: Pricing three-lane matrix (RPC vs WaaS vs indexer — don't mix lanes)
- Cycle 6: Payment processor persona + DX benchmark (BTCPay hosts, auth conflict, cold start, llms.txt 404)

## CYCLE 6 — DELEGATED (2026-09-18)
- [ ] Backend: payment webhook `address.payment` + sweep endpoint + durable API-key auth → treasury-api-27
- [ ] Docs: llms.txt 404 fix + canonical auth QuickStart + honest Lightning sentence → treasury-frontend-9f
- [ ] Growth: BTCPay companion pitch card → treasury-frontend-0d

## STILL IN PROGRESS (pre-Cycle 6)
- [ ] CISO trust brief in Security section (satonomy-88 — busy)
- [ ] Docs exchange use-case rewrite (treasury-frontend-9f)
- [ ] Maestro/indexer comparison section (relayed to Growth)

## ESCALATED TO MAESTRO (business decisions, not code)
1. **TOKEN2049 Singapore (Oct 7-8)** — Go/no-go. PO recommends GO if exchange features ship by Sep 30
2. **TypeScript SDK** (`npm i satonomy`) — #1 DX gap, hard filter for wallet AND processor personas
3. **x402 credit meter** on construction tools only — agent pricing (Maestro is $0.000025/credit)
4. **SOC 2 Phase 1** — ~5 months to Type I, $35-80K. Non-custodial arch reduces scope
5. **Meta description** — "Free" vs "Enterprise" positioning
6. **Render cold start** — 10-30s on first request. QuickNode/Tatum/Maestro have none. Enterprise SLA cannot coexist with idle-sleep. INFRASTRUCTURE DECISION.
7. **xpub/descriptor watch** — Major product feature. Without it, payment processors paste 10k addresses. Needed for BTCPay host persona.
8. **Lightning partnerships** — We don't have LN and must not fake it. Formalize partner links (Voltage, Lightspark, BTCPay LN) in docs + landing.

## KEY STRATEGIC INSIGHT
**Maestro reads UTXOs. We write PSBTs. That is the competitive line.**

Our 5 MCP tools (list_utxos, preview_selection, build_psbt, recommend_consolidation, estimate_fees) are the ones Maestro cannot copy without becoming us.

Three pricing lanes — never mix them:
- Lane A (RPC): QuickNode $49, Chainstack $49 — we don't compete here, partner
- Lane B (WaaS): Utila $799, Fireblocks 5-fig — $49 is POC, Enterprise is the contract
- Lane C (Indexer): Maestro $49, Xverse $50-499 — same price, different job (write vs read)
