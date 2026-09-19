# Treasure Bots

Architecture Decision Records for the Satonomy Maestri agent fleet.

Twenty-four agents. One Bitcoin API company. The fleet exists to ship `treasury-api` and `treasury-frontend` — and nothing else.

## Repos in scope

- `treasury-api`
- `treasury-frontend`

No other Satonomy repos. Agents that wander off-repo get a Sentinel ping.

## Hierarchy

```
Mega Brain (CEO)                    Claude Opus 4.6 · maestro
├── CTO                             Claude Opus 4.6 · maestro
│   ├── API Engineer                Composer 2.5
│   ├── Gateway Engineer            Grok 4.6
│   ├── Frontend Engineer           Composer 2.5
│   ├── DevOps                      Grok 4.6
│   ├── Security Engineer           Claude Opus 4.6
│   ├── QA Verifier                 Claude Opus 4.6
│   ├── SDK Engineer                Composer 2.5
│   ├── Designer                    Composer 2.5   (also reports to HoP)
│   └── Docs Engineer               Claude Opus 4.6 (also reports to HoP)
├── Head of Product                 Claude Opus 4.6 · maestro
│   ├── Product Analyst             Grok 4.6
│   ├── Designer                    (shared with CTO)
│   └── Docs Engineer               (shared with CTO)
├── Head of Marketing               Claude Opus 4.6 · maestro
│   ├── Content Marketing           Composer 2.5
│   ├── Growth Marketing            Grok 4.6
│   └── DevRel                      Claude Opus 4.6
├── COO                             Grok 4.6
│   ├── Legal                       Claude Opus 4.6   (not activated)
│   ├── Sales                       Composer 2.5      (not activated)
│   ├── Support                     Grok 4.6          (not activated)
│   └── Finance                     Grok 4.6          (not activated)
├── Sentinel                        Grok 4.6          (watchdog)
└── Estagiario Grok                 Grok 4.6          (standalone utility)
```

## Model cost tiers

| Tier | Binary | Model | Use for |
|------|--------|-------|---------|
| High | `claude` | Claude Opus 4.6 | Executives, security, QA, legal, docs, DevRel, marketing lead |
| Mid | `grok` | Grok 4.6 | COO, Sentinel, gateway, DevOps, growth, analyst, support, finance, intern |
| Fast | `/Users/wiso/.local/bin/agent` | Composer 2.5 | Implementation: API, frontend, SDK, designer, content, sales |

Orchestrators (Mega Brain, CTO, Head of Product, Head of Marketing) run as `maestro` so they can recruit and delegate. They do not own files.

## Recruit

```bash
maestri recruit "Mega Brain" --command maestro --role "CEO"
maestri recruit "CTO" --command maestro --role "CTO"
maestri recruit "Head of Product" --command maestro --role "Head of Product"
maestri recruit "Head of Marketing" --command maestro --role "Head of Marketing"

maestri recruit "API Engineer" --command /Users/wiso/.local/bin/agent --role "API Engineer"
maestri recruit "Frontend Engineer" --command /Users/wiso/.local/bin/agent --role "Frontend Engineer"
maestri recruit "SDK Engineer" --command /Users/wiso/.local/bin/agent --role "SDK Engineer"
maestri recruit "Designer" --command /Users/wiso/.local/bin/agent --role "Designer"
maestri recruit "Content Marketing" --command /Users/wiso/.local/bin/agent --role "Content Marketing"
maestri recruit "Sales" --command /Users/wiso/.local/bin/agent --role "Sales"

maestri recruit "COO" --command grok --role "COO"
maestri recruit "Sentinel" --command grok --role "Sentinel"
maestri recruit "Gateway Engineer" --command grok --role "Gateway Engineer"
maestri recruit "DevOps" --command grok --role "DevOps"
maestri recruit "Product Analyst" --command grok --role "Product Analyst"
maestri recruit "Growth Marketing" --command grok --role "Growth Marketing"
maestri recruit "Support" --command grok --role "Support"
maestri recruit "Finance" --command grok --role "Finance"
maestri recruit "Estagiario Grok" --command grok --role "Estagiario"

maestri recruit "Security Engineer" --command claude --role "Security Engineer"
maestri recruit "QA Verifier" --command claude --role "QA Verifier"
maestri recruit "Docs Engineer" --command claude --role "Docs Engineer"
maestri recruit "DevRel" --command claude --role "DevRel"
maestri recruit "Legal" --command claude --role "Legal"
```

Exact flags live in each ADR under **Recruit Command**.

## Restore

1. Open the Maestri workspace.
2. Recruit from the ADR command if the terminal is gone.
3. Paste **Mission**, **Repos**, and **Context / Memories** from the ADR as the first prompt.
4. Set status: PARKED agents stay idle until a manager unparks them. BLOCKED agents need the listed blocker cleared first.
5. COO and Sentinel resume their loops last so they do not fire on a half-restored canvas.

## Status snapshot (Sprint 2)

| Status | Agents |
|--------|--------|
| ACTIVE | Mega Brain, CTO, Head of Product, Head of Marketing, COO, Sentinel, Estagiario Grok |
| PARKED | API (85.6% context), Frontend (46.2%), Gateway, DevOps (HOLD — DNS is operator), Security, QA, Designer, Docs (80.5%), Content, Growth, DevRel, Product Analyst |
| BLOCKED | SDK Engineer (npm token) |
| Not activated | Legal, Sales, Support, Finance |

## ADRs

See [`agents/`](agents/). One file per agent, numbered 00–23.
