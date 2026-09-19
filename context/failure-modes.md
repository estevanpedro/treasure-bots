# Failure Modes & Safety Rails

Based on analysis of 1,600+ multi-agent execution traces.

## The 3 Failure Categories

### 1. Specification Failures — 42% of all failures
**What:** Agents don't know what to do or do the wrong thing
**Cause:** Prose-style "just build something cool" instructions
**Fix:** Every task must include:
- Clear objective (1 sentence)
- Input data/context (what they receive)
- Output format (what they produce)
- Acceptance criteria (how we know it's done)
- Explicit exclusions ("you do NOT handle X")

### 2. Coordination Failures — 37% of all failures
**What:** Agents conflict, duplicate work, or lose sync
**Cause:** Peer-to-peer chaos, no central authority
**Fix:** 
- Hub-and-spoke through Maestro
- One agent owns each resource
- Structured handoff with task IDs
- Never let two agents edit the same file

### 3. Verification Failures — 21% of all failures
**What:** Bad output reaches production unchecked
**Cause:** No independent review
**Fix:**
- Dedicated Verifier agent (isolated, can't be influenced)
- Every critical output goes through Verifier
- Max 2 retry rounds, then escalate
- PwC saw 7x accuracy improvement with this pattern

---

## Circuit Breakers

| Trigger | Action |
|---------|--------|
| Agent fails same task 2x | Escalate to Maestro |
| Agent produces no output for 5min | Maestro checks status |
| Two agents claim same resource | Maestro arbitrates immediately |
| Token budget exceeded | Pause and report to Maestro |
| Consensus note not updated for 2 cycles | Maestro forces checkpoint |

---

## Cost Optimization

- Use **cheaper models (Grok)** for: routine tasks, boilerplate, simple lookups, formatting, repetitive operations
- Use **Claude models** for: creative problem-solving, architecture decisions, complex debugging, security analysis, strategic thinking
- **Verifier** should always use a strong model (independent judgment matters)
- **Product Strategist** benefits from strong model (creative/strategic)
- **Platform Engineer** can often use cheaper model (structured ops tasks)

---

## Monitoring Checklist

- [ ] Are all agents responding? (maestri check)
- [ ] Is the Consensus note being updated?
- [ ] Are tasks moving through cycles (Plan → Execute → Verify → Ship)?
- [ ] Are any agents stuck in retry loops?
- [ ] Is token spend within budget?
- [ ] Are Verifier pass rates healthy (>80%)?
