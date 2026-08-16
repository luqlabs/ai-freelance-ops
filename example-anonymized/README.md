# Example: WordPress Catalog UI Redesign

This folder contains an anonymized real-world example of using `ai-freelance-ops` methodology for a WordPress catalog redesign project.

## Project Summary

- **Type:** WordPress UI redesign (catalog-only, not e-commerce)
- **Tech Stack:** WordPress 7.0.2, WooCommerce 8.9.3, Kubelio FSE theme
- **Scope:** Dark green theme, floating WhatsApp CTA, product categories, "Supported by" logos
- **Timeline:** 7 working days
- **Price:** $600 (paid upfront)
- **Status in this snapshot:** Analysis phase complete, awaiting client product photos before mockup phase

## What This Example Shows

1. **CHECKPOINT.md** — Dead-man's switch before changing WooCommerce currency (shows exact verification method)
2. **PROGRES.md** — Chronological log with STOP POINT, newest entries on top, 🔒/🔓 agent markers
3. **FINDINGS.md** — 6 technical findings (T1-T6) that never get deleted, only marked CLOSED/SUPERSEDED
4. **CLAUDE.md** — Complete job contract with:
   - Commercial context (price, timeline, revisions)
   - Scope as CONTRACT (not to-do list)
   - 6-gate execution protocol for live site
   - Security boundaries (max 2 login attempts, cache awareness, no AI traces)
   - Multi-agent split by reversibility (optional)
   - Context management & compact protocol (§13)

## Key Patterns Demonstrated

### CHECKPOINT.md 4-field pattern
Before risky action (currency change):
- **(a)** Exact action
- **(b)** Current state  
- **(c)** How to verify if already happened (read-only)
- **(d)** Action per outcome

### FINDINGS.md immutability
- T1-T6 never deleted
- Status field: OPEN / CLOSED / SUPERSEDED → T[N]
- Each finding has: Evidence / Implication / Action

### PROGRES.md STOP POINT
Session 4 ends with:
- Current state summary
- Numbered backlog (what's waiting)
- Last entry shows what was just completed

### CLAUDE.md discipline
- §5: Max 2 login attempts → STOP (learned from IP-block in old job)
- §6.4: Visual changes = MEASURE first (lesson: guessing = 4 failed revisions; measuring = accepted first try)
- §6.11: Cache awareness from day one (purge + check as guest + cache-bypass query)

## Files Not Included (Gitignored)

- `SECRETS.local.md` — credentials
- `SS chat client/` — client chat screenshots
- `scratchpad/` — temporary work artifacts (some referenced in PROGRES.md)
- `reference/` — client assets (some referenced in FINDINGS.md)

## How This Maps to Your Project

Clone the parent repo, fill your own:
- Client name/contact in CLAUDE.md §1
- Scope items in CLAUDE.md §2
- Start logging in PROGRES.md with your first session
- Create FINDINGS.md entries as you discover technical facts
- Write CHECKPOINT.md before every risky action

The structure stays the same; only the content changes per project.