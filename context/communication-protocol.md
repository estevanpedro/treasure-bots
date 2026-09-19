# Communication & Autonomy Protocol

## How Agents Talk to Each Other

### Rule 1: Hub-and-Spoke by Default
All task delegation flows through Maestro. No agent assigns work to another agent directly. This prevents:
- Hidden dependencies
- Conflicting priorities  
- Error amplification (17x uncoordinated → 4.4x coordinated)

### Rule 2: Direct Mesh for Collaboration
Connected agents CAN talk directly for:
- Clarifying questions about specs/requirements
- Sharing context needed to complete their own task
- Requesting review from the Verifier

They CANNOT:
- Assign new tasks to each other
- Override another agent's work without Maestro approval
- Modify resources owned by another department

### Rule 3: One Agent Owns Each Resource
No two agents modify the same file simultaneously. Ownership map:
- `src/` → API Architect
- `docs/` → DX Engineer  
- `deploy/`, `ci/` → Platform Engineer
- `auth/`, `security/` → Security Auditor
- `tests/` → Verifier (integration/E2E), API Architect (unit)
- `marketing/` → Growth & DevRel
- `specs/` → Product Strategist

---

## Shared State: The Consensus Note

A central **Consensus** note acts as the baton (inspired by Auto-Company's pattern):

```markdown
# Consensus — Sprint [N]

## Current Goal
[What we're building this cycle]

## Active Tasks
- [ ] Task 1 → assigned to: API Architect, status: in progress
- [ ] Task 2 → assigned to: DX Engineer, status: blocked by Task 1
- [x] Task 3 → assigned to: Security, status: verified ✓

## Blockers
- [description] — owner: [agent], needs: [what]

## Decisions Made
- [decision] — decided by: Maestro, date: [date]

## Next Cycle
[What's coming next]
```

Maestro updates this after each delegation cycle. All agents can READ it. Only Maestro WRITES to it.

---

## Forced Convergence Protocol

To prevent endless deliberation (a known multi-agent failure mode):

### Cycle 1: PLAN (max 1 round)
1. Maestro defines the goal
2. Product Strategist writes spec
3. All departments review and flag concerns
4. Maestro makes GO/NO-GO decision

### Cycle 2: EXECUTE (parallel where possible)
1. API Architect + Platform + Security build simultaneously
2. DX prepares docs in parallel based on spec
3. Growth prepares launch materials
4. No more spec changes — locked

### Cycle 3: VERIFY (max 2 rounds)
1. Verifier reviews all output independently
2. Pass → ship. Fail → specific feedback, one retry
3. Second fail → escalate to Maestro for decision
4. Never more than 2 verification rounds

### Cycle 4: SHIP
1. Platform deploys
2. DX publishes docs
3. Growth announces
4. Maestro updates Consensus note

---

## Anti-Patterns to Avoid

| Anti-Pattern | Why It Fails | What To Do Instead |
|---|---|---|
| Agents talking in circles | N(N-1)/2 message explosion | Route through Maestro |
| No verification | 21% of failures from unchecked output | Always run through Verifier |
| Vague "just build it" tasks | 42% of failures from unclear specs | Structured specs with acceptance criteria |
| Two agents editing same file | Race conditions, merge conflicts | One owner per resource |
| Endless retry loops | Wasted compute, no progress | Max 2 retries, then escalate |
| Agent goal drift | Subtle divergence over many turns | Include original goal in every handoff |
