# Real API Company Structures

How the biggest API-as-a-Service companies actually organize their teams.

---

## Stripe

Two macro groups:

**Product Development** (organized by product)
- Payments (core checkout, payment intents)
- Billing (subscriptions, invoicing, metering)
- Connect (marketplace/platform payments)
- Terminal (in-person payments)
- Radar (ML-powered fraud detection)
- Treasury (banking-as-a-service)
- Identity (KYC/verification)

**Infrastructure & Operations**
- API Platform — the backbone: load balancers, web framework, databases, Kafka, Kubernetes
- API Review — cross-functional review for EVERY API surface change (not just code review)
- ML Engineering — powers Radar and risk scoring
- Security Engineering — dedicated team, not embedded
- Developer Experience — docs quality is part of engineering career ladders; docs team IS engineering
- Global Payments Network — money movement infrastructure
- Developer Productivity — internal tooling for engineers

**Key insight:** Stripe treats DX as engineering, not marketing. Docs quality is a promotion criterion.

---

## Twilio

Small autonomous squads (5–10 people), each with 3 balanced leaders:
- **Product Manager** — the "CEO" of the squad (what & why)
- **Engineering Lead** — the "COO" (how & when)
- **Architect** — alignment between local decisions and company-wide strategy

**Product-organized teams:**
- Programmable Voice
- Programmable SMS/Messaging
- Programmable Video
- SendGrid (Email API) — kept as separate unit post-acquisition
- Twilio Verify (auth/2FA)
- Twilio Segment (CDP)
- Twilio Flex (contact center)

**Platform teams (shared):**
- Super Network — global telecom infrastructure
- API Platform — shared gateway, rate limiting, auth
- Developer Experience — docs, SDKs, quickstarts, console
- Trust & Security — compliance, fraud prevention
- Billing & Metering — usage tracking across all products

**Key insight:** Evolved from functional groupings (by expertise) to business-unit groupings (by product) at scale.

---

## Plaid

**Core teams:**
- Link (the frontend connection widget)
- API Products (Transactions, Auth, Identity, Assets, Investments, Liabilities)
- Institution Connectivity — integrations with 12,000+ banks
- Risk & Compliance — heavily regulated (financial data)
- Developer Experience — sandbox environment, docs, SDKs
- Platform & Infrastructure — uptime is existential (banks depend on them)
- Data Quality — dedicated team for data accuracy/freshness

**Key insight:** Data quality has its own team because their product IS data. Compliance is massive due to financial regulations.

---

## SendGrid (now part of Twilio)

**Pre-acquisition structure:**
- Email Delivery Engine — the core SMTP/API infrastructure
- Email Validation — address verification service
- Marketing Campaigns — template builder, analytics
- Developer Experience — SDKs in 7 languages, docs, examples
- Deliverability — inbox placement, ISP relations, reputation management
- Compliance & Anti-Spam — CAN-SPAM, GDPR, abuse detection
- Platform/SRE — sending billions of emails requires serious infra

**Key insight:** Deliverability is its own team because email reputation is the moat. Anti-spam/compliance is critical — one bad actor can burn the whole platform's IP reputation.

---

## Clearbit (now part of HubSpot)

**Pre-acquisition structure:**
- Data Engineering — enrichment APIs, data pipelines, entity resolution
- API Products — Enrichment, Reveal, Prospector, Risk
- Data Quality & Sourcing — web crawlers, data partnerships, accuracy
- Developer Experience — docs, SDKs, webhooks, Zapier integration
- Go-to-Market — self-serve signup, developer-led growth
- Customer Success — helping enterprise customers maximize value

**Key insight:** Small team (~150 people), so departments were lean. Data sourcing/quality was the competitive moat.

---

## Common Departments Across ALL API Companies

| Department | Stripe | Twilio | Plaid | SendGrid | Clearbit |
|-----------|--------|--------|-------|----------|----------|
| Core API Engineering | ✅ | ✅ | ✅ | ✅ | ✅ |
| API Platform / Gateway | ✅ | ✅ | ✅ | ✅ | — |
| Developer Experience | ✅ | ✅ | ✅ | ✅ | ✅ |
| Security / Compliance | ✅ | ✅ | ✅ | ✅ | — |
| Billing / Metering | ✅ | ✅ | — | — | — |
| Data Quality | — | — | ✅ | ✅ | ✅ |
| Platform / SRE | ✅ | ✅ | ✅ | ✅ | — |
| Growth / DevRel | ✅ | ✅ | — | ✅ | ✅ |
| Product (per-product) | ✅ | ✅ | ✅ | ✅ | ✅ |

**Universal (every API company has these):**
1. Core API Engineering
2. Developer Experience
3. Product Management
4. Platform / Infrastructure

**Common (most have):**
5. Security & Compliance
6. Billing & Metering
7. Growth / DevRel

**Domain-specific (depends on product):**
8. Data Quality (if data product)
9. Deliverability (if messaging product)
10. Institution Connectivity (if fintech)
