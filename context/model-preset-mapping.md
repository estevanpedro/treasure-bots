# Model & Preset Mapping Per Employee

## Available Models

| Command | Model | Cost | Strengths |
|---|---|---|---|
| `claude` (preset: Claude Code) | Claude Opus 4.6 | $$$ | Strategy, creative thinking, security analysis, architecture, complex reasoning |
| `/Users/wiso/.local/bin/agent` | Cursor Composer 2.5 | $ | Code generation, implementation, refactoring — matches Opus on coding benchmarks at ~1/10th cost |
| `grok` | Grok 4.6 | $ | Routine ops, configs, boilerplate, repetitive tasks, data processing |

---

## Full Agent Mapping (20 Employees)

### EXECUTIVE — Claude Opus (needs best judgment)

| # | Role | Command | Why Opus |
|---|------|---------|----------|
| 0 | **CEO / Maestro** | `claude` (preset) | Strategic decisions, cross-team coordination, conflict resolution |
| 1 | **CTO** | `claude` (preset) | Architecture decisions, tech vision, build-vs-buy |

### PRODUCT — Mixed

| # | Role | Command | Why |
|---|------|---------|-----|
| 2 | **Head of Product** | `claude` (preset) | Product strategy, competitive analysis — needs creative + analytical |
| 3 | **Product Analyst** | `grok` | Data queries, metrics, dashboards — structured/repetitive |

### ENGINEERING — Mostly Composer 2.5 (code-heavy, well-scoped)

| # | Role | Command | Why |
|---|------|---------|-----|
| 4 | **Lead API Engineer** | `/Users/wiso/.local/bin/agent` | Core coding — Composer 2.5 excels at implementation |
| 5 | **Platform/Gateway Eng** | `grok` | Gateway configs, rate limits, routing — structured/templated |
| 6 | **Frontend Engineer** | `/Users/wiso/.local/bin/agent` | UI components, React — Composer strong at frontend |
| 7 | **DevOps / SRE** | `grok` | CI/CD, deploy scripts, monitoring configs — ops tasks |
| 8 | **Security Engineer** | `claude` (preset) | Threat modeling, security audits — needs deep reasoning |
| 9 | **QA / Verifier** | `claude` (preset) | Independent quality judgment — can't cut corners here |
| 10 | **SDK Engineer** | `/Users/wiso/.local/bin/agent` | SDK gen from spec — Composer great at mechanical code |

### DESIGN — Composer 2.5

| # | Role | Command | Why |
|---|------|---------|-----|
| 11 | **UX / Designer** | `/Users/wiso/.local/bin/agent` | Design specs, wireframes, component patterns |

### MARKETING — Mixed

| # | Role | Command | Why |
|---|------|---------|-----|
| 12 | **Head of Marketing** | `claude` (preset) | Strategy, positioning, brand voice — creative + strategic |
| 13 | **Content Marketing** | `/Users/wiso/.local/bin/agent` | Blog posts, tutorials — needs quality writing |
| 14 | **Growth Marketing** | `grok` | Campaign setup, landing page tweaks, metrics — structured |
| 15 | **DevRel** | `claude` (preset) | Community engagement, talks, demos — needs personality |

### SALES & SUPPORT — Mostly Grok (templated work)

| # | Role | Command | Why |
|---|------|---------|-----|
| 16 | **Head of Sales** | `/Users/wiso/.local/bin/agent` | Proposals, outreach, deal negotiation |
| 17 | **Customer Support** | `grok` | Ticket responses, FAQ, common issues — templated |

### OPERATIONS — Grok (structured/numerical)

| # | Role | Command | Why |
|---|------|---------|-----|
| 18 | **Finance / Ops** | `grok` | Billing, invoices, cost tracking — structured numerical |
| 19 | **Legal / Compliance** | `claude` (preset) | Legal docs need precision, compliance needs careful reasoning |

---

## Cost Distribution

| Tier | Model | Count | Roles |
|------|-------|-------|-------|
| **High ($$$)** | Claude Opus | 7 | CEO, CTO, Head of Product, Security, QA, Head of Marketing, DevRel, Legal |
| **Mid ($)** | Composer 2.5 | 6 | API Eng, Frontend, SDK, Designer, Content Mkt, Sales |
| **Low ($)** | Grok | 5 | Analyst, Gateway, DevOps, Growth Mkt, Support, Finance |

~35% high-cost, ~30% mid-cost, ~35% low-cost.

---

## Management Hierarchy

```
                         CEO (Mega Brain) — Claude Opus
                              │
          ┌───────┬───────────┼───────────┬──────────┬──────────┐
          ▼       ▼           ▼           ▼          ▼          ▼
        CTO    Product    Marketing    Sales     Support    Ops/Legal
       Opus    Opus       Opus        Composer   Grok       Grok/Opus
     manages:  manages:   manages:
     ├ API Eng (Composer)  ├ Content (Composer)
     ├ Gateway (Grok)      ├ Growth (Grok)
     ├ Frontend (Composer) └ DevRel (Opus)
     ├ DevOps (Grok)
     ├ Security (Opus)
     ├ QA (Opus)
     ├ SDK (Composer)
     └ Designer (Composer)
```

---

## Recruit Commands Cheatsheet

```bash
# EXECUTIVE
# CEO = you (Mega Brain, already running)
maestri recruit "CTO" --preset "Claude Code" --role "CTO"

# PRODUCT
maestri recruit "Head of Product" --preset "Claude Code" --role "Head of Product"
maestri recruit "Product Analyst" --command grok --role "Product Analyst"

# ENGINEERING
maestri recruit "API Engineer" --command /Users/wiso/.local/bin/agent --role "Lead API Engineer"
maestri recruit "Gateway Engineer" --command grok --role "Platform Gateway Engineer"
maestri recruit "Frontend Engineer" --command /Users/wiso/.local/bin/agent --role "Frontend Engineer"
maestri recruit "DevOps" --command grok --role "DevOps SRE"
maestri recruit "Security Engineer" --preset "Claude Code" --role "Security Engineer"
maestri recruit "QA Verifier" --preset "Claude Code" --role "QA Verifier"
maestri recruit "SDK Engineer" --command /Users/wiso/.local/bin/agent --role "SDK Engineer"

# DESIGN
maestri recruit "Designer" --command /Users/wiso/.local/bin/agent --role "UX Designer"

# MARKETING
maestri recruit "Head of Marketing" --preset "Claude Code" --role "Head of Marketing"
maestri recruit "Content Marketing" --command /Users/wiso/.local/bin/agent --role "Content Marketing"
maestri recruit "Growth Marketing" --command grok --role "Growth Marketing"
maestri recruit "DevRel" --preset "Claude Code" --role "DevRel"

# SALES & SUPPORT
maestri recruit "Sales" --command /Users/wiso/.local/bin/agent --role "Head of Sales"
maestri recruit "Support" --command grok --role "Customer Support"

# OPERATIONS
maestri recruit "Finance" --command grok --role "Finance Operations"
maestri recruit "Legal" --preset "Claude Code" --role "Legal Compliance"
```
