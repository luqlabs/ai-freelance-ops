# ai-freelance-ops

> Operational methodology for AI-assisted freelance work on live client systems.

Not a new framework. Not a plugin. This is a **work template** you can clone and use immediately for AI-powered freelance projects — especially those touching live systems (WordPress, CMS, servers).

---

## Problem Solved

When using AI agents (Claude Code, Codex, etc.) for freelance work on live client systems, real risks emerge:
- Session dies mid-task → no idea what already changed
- Blind retries → IP blocks, corrupted data, site downtime
- Cache hides results → false "it's done" claims
- Two agents collide → file overwrites, inconsistent state
- Credentials leak via chat/code

This methodology answers all of that with 5 unique components.

---

## 5 Core Components

### 1. CHECKPOINT.md — Dead-Man's Switch
Before every risky action, write 4 fields:
- **(a)** exact action about to run
- **(b)** current state
- **(c)** how to verify whether action already happened (read-only)
- **(d)** action per outcome

If session dies badly, new session can resume without asking — just read CHECKPOINT.md.

### 2. PROGRES.md — Single Source of Truth
Chronological log, newest on top, with a STOP POINT marker at end of each session. No status in other files.

### 3. TEMUAN.md — Immutable Issue Tracker
Technical findings with IDs (T1, T2, ...). Never deleted — only CLOSED or SUPERSEDED with forward references. Creates permanent audit trail for clients.

### 4. 6-Gate Execution Protocol
For ALL touches to live systems:
1. Read-only diagnosis + evidence
2. Write CHECKPOINT.md
3. Report plan → wait for operator go
4. 1 change → verify with evidence → log in PROGRES → then continue
5. Fails once = STOP & think (not blind retry)
6. Claim "done" only with concrete evidence

### 5. Agent Split by Reversibility
Not split by skill, but by **risk**:
- **Lead Agent (expensive model):** everything touching live, login, architectural decisions
- **Support Agent (cheap/free model):** everything reversible — research, backup, post-action verification, housekeeping

---

## Usage

```bash
git clone https://github.com/luqlabs/ai-freelance-ops.git client-project-name
cd client-project-name
rm -rf .git
git init
```

Then fill:
1. `CLAUDE.md` — client context, scope, timeline
2. `SECRETS.local.md` — credentials (already in .gitignore)
3. Start logging in `PROGRES.md`

---

## File Structure

```
CLAUDE.md           ← brain & job contract
PROGRES.md          ← single source of status
TEMUAN.md           ← immutable technical findings with IDs
CHECKPOINT.md       ← dead-man's switch pre-action
SECRETS.local.md    ← credentials (gitignored)
SS chat client/     ← client chat screenshots (gitignored)
reference/          ← client assets & mockups
scratchpad/         ← temporary work artifacts
hasil-preview/      ← before/after PNGs for client
assets/             ← final artifacts to client system
```

---

## Real Example

`example-anonymized/` folder contains an example from a WordPress catalog UI redesign project — all client data anonymized.

---

## What Makes This Unique

Research across GitHub found no public repo combining these 5 patterns:

1. **Dead-man's switch idempotency** — 4-field pre-action record (exact action + current state + verification method + recovery path) not found in any checkpoint system
2. **6-gate live-site protocol** with IP-block & cache awareness — not code-repo gates
3. **Asymmetric agent split by reversibility** (not skill) — model tier as risk control
4. **TEMUAN.md immutability rule** — forbids deletion, only CLOSED/SUPERSEDED banners with forward refs
5. **Freelance commercial context built-in** — scope-as-contract, revision tracking, credential rotation discipline

This convergence is designed specifically for **solo freelancers doing live client work with AI agents** where mistakes have commercial cost (revision penalty, IP block, client trust), not just technical impact.

---

## License

MIT