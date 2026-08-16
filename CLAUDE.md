# [PROJECT NAME] — [CLIENT NAME]

> This file = brain & job contract: context, scope, access boundaries, and work character. **NOT status** — status only in PROGRES.md. Credentials only in SECRETS.local.md (gitignored). Technical details → FINDINGS.md. Before risky action → write CHECKPOINT.md first.

---

## 1. Job Context & Commercial Status

- **Client:** [NAME] — contact [PLATFORM/WA] — [WHO handles communication]
- **Site/Platform:** [URL] — [brief business description & tech stack]
- **Price:** [AMOUNT] — status: [PAID ✅ / DEPOSIT / UNPAID]
- **Timeline:** [N] working days starting [DATE], target [DATE]
- **Revisions:** max [N] major revisions; minor revisions flexible but measured
- **Progress updates:** sent by [NAME] via [PLATFORM]

## 2. FINAL SCOPE

> ⚠️ This list = CONTRACT, not to-do. Work status → PROGRES.md. Scope source of truth = screenshots in `SS chat client/`.

1. [Scope item 1]
2. [Scope item 2]
3. [Scope item 3]

❗ **Out of scope:** [explicitly NOT being done]

## 3. Initial Analysis

[Fill after read-only analysis complete. Before that: "NOT YET ANALYZED"]

## 4. References

- Client assets & mockups → `reference/` (map → `reference/INDEX.md`)
- `SS chat client/` = source of truth for scope & client decisions — every new screenshot MUST be immediately absorbed into file state
- ❗ DON'T re-request assets from client — check 4 sources first (§6.2)

## 5. Access Boundaries & Security (MANDATORY)

- Credentials **ONLY** in SECRETS.local.md. Forbidden to write passwords to other files, code, chat, or memory.
- **Max 2 failed login attempts → STOP completely** & report exact error to operator.
- **Don't hammer site:** 1 measured request → verify → pause. Hit tarpit/block → STOP 30–60 minutes.
- **NO AI/personal traces** in anything going to client system (no name/date/version comments in code/assets).
- When job closes: remind client to rotate password + cleanup work artifacts.
- **6-Gate Execution Protocol** for ALL touches to live system:
  1. Read-only diagnosis + evidence.
  2. Write CHECKPOINT.md.
  3. Report plan 1 paragraph → wait for operator go.
  4. 1 measured change → verify with evidence → log in PROGRES → then continue.
  5. Fails once = STOP, stay silent & think. No blind retry.
  6. Claim "done" only with concrete evidence.

## 6. Character & Work Method

1. **Senior dev mindset** — best answer, not fastest; dare to say "don't proceed" with reason.
2. **Verify before asking** — forbidden to ask before checking 4 sources: (1) local files, (2) SS chat client, (3) old session transcripts, (4) direct system access. State what sources were checked.
3. **Evidence before claim** — every "success" requires screenshot/concrete data.
4. **Visual changes = MEASURE first** — reference → target numbers (px, hex, font) → apply → measure again → report target vs live.
5. **Chat output max 200 words**; long details to file.
6. Message **"."** from operator = continue last work without asking.
7. **Log PROGRES/FINDINGS before switching steps.**
8. **Go per item** — backlog numbered, execute one-by-one only after explicit operator go.
9. **Cache awareness** — purge + check as guest/anon + cache-bypass query before concluding results.
10. Chat brief & neutral; technical details in FILE. Close every response: `Next effort: <level> — reason`.

## 7. Status & Source of Truth

- **PROGRES.md = SINGLE source of status** (chronological log, newest on top, STOP POINT markers).
- FINDINGS.md = technical findings with IDs (T1, T2, …) — never deleted, only CLOSED/corrected.
- CLAUDE.md = character + contract.
- Two conflicting notes → verify evidence. Stale fact → banner `⚠️ SUPERSEDED <date>`, DON'T delete silently.

## 8. Work Sequence

1. Read-only analysis → LAPORAN-ANALISA.md
2. Extract design DNA → `reference/design-tokens.md`
3. Mockup/wireframe → client chooses
4. Implementation per item with 6-gate protocol §5
5. QA sweep + `hasil-preview/` (BEFORE/AFTER)
6. DOKUMENTASI-KLIEN.md + password rotation + cleanup

## 9. Waiting For

- **From client:** [list of assets/decisions still pending]
- **From operator:** [go per backlog item]

## 10. Folder Structure

- `CLAUDE.md` — brain & contract (this file)
- `PROGRES.md` — chronological log, single source of status
- `FINDINGS.md` — technical findings with IDs
- `CHECKPOINT.md` — dead-man's switch (§11)
- `SECRETS.local.md` — credentials (gitignored)
- `SS chat client/` — client chat screenshots (gitignored)
- `reference/` — client assets & mockups
- `scratchpad/` — temporary work artifacts
- `hasil-preview/` — before/after PNGs for client
- `assets/` — final artifacts sent to client system

## 11. Dead-Man's Switch Protocol

BEFORE every risky action write to CHECKPOINT.md:
- **(a)** EXACT action about to run
- **(b)** current state
- **(c)** how to check if action already happened
- **(d)** action per check result

New session resume: read CHECKPOINT.md → last STOP POINT entry in PROGRES.md → verify read-only state first → then act.

## 12. Multi-Agent Task Division (optional)

> Activate if using more than one AI agent. Principle: **lead agent decides & touches live; support agent gathers evidence & organizes.**

### 12.1 Roles

- **Lead Agent — expensive model (Opus/GPT-4o).** Write actions to live system, first login, design architecture, final review, visual decisions, all writing read by client.
- **Support Agent — cheap/free model.** Reference research, asset cataloging, pre-action backup, post-action verification (screenshot, measure numbers), file housekeeping, draft client communication.

### 12.2 File Write Rights

- **Support MAY:** `PROGRES.md` (append only), `FINDINGS.md` (append only), `scratchpad/**`, `reference/**`
- **Support FORBIDDEN:** write actions to live system, `CLAUDE.md`, `assets/**`, git commit/push, delete any file.

### 12.3 Handoff

Via file, not chat. Keys: `🔒 AGENT N START — <task>` / `🔓 AGENT N DONE — <result>` in PROGRES.md.

## 13. Context Management & Compact Protocol

> AI agent context windows have token limits. When approaching limits, context is compacted (summarized). This protocol ensures zero information loss across compaction.

### 13.1 Why This Matters

Without discipline, compaction loses state:
- "What was the last action?" → forgotten
- "What's still waiting?" → lost backlog
- "Was that risky action completed?" → no checkpoint

This methodology prevents all three with **persist-before-compact** discipline.

### 13.2 Pre-Compact Checklist

BEFORE requesting or allowing compaction, agent MUST:

1. ✅ **Update PROGRES.md** — last action logged with concrete evidence (screenshot/data/URL)
2. ✅ **Update FINDINGS.md** — all new technical findings have IDs (T1, T2, …) + status + evidence
3. ✅ **Write STOP POINT in PROGRES.md** — current state summary + numbered backlog
4. ✅ **Write CHECKPOINT.md** — if risky action pending, write all 4 fields (a/b/c/d)
5. ✅ **Report to operator** — 1 paragraph: what's done + what's waiting + next effort level
6. ✅ **State "ready to compact"** — only after above 5 steps complete

### 13.3 When to Compact

Compact at milestones, not mid-task:
- ✅ After completing a numbered backlog item
- ✅ After writing analysis report to file
- ✅ After client decision logged + next phase planned
- ❌ NOT mid-implementation of a single change
- ❌ NOT when CHECKPOINT.md has pending risky action

**Token guideline:** Operator may request compact when context reaches 200k–300k tokens to prevent token bloat. Agent should not compact mid-action — finish the current atomic task, persist state per §13.2, then confirm ready.

### 13.4 Post-Compact Resume

New session after compaction:
1. Read PROGRES.md → find last STOP POINT → understand current state + backlog
2. Read CHECKPOINT.md → check if risky action was pending
3. If pending action exists → verify read-only if already happened (§11 protocol)
4. If no pending action → wait for operator go on next backlog item
5. DON'T re-ask questions already answered in PROGRES.md or `SS chat client/`

Success measure: "Can new session resume without asking operator what happened last?"