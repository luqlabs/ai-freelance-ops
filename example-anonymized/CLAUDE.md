# Catalog UI Redesign — example-client.com

> This file = brain & job contract: context, scope, access boundaries, and work character. **NOT status** — work status only in PROGRES.md. Credentials only in SECRETS.local.md (gitignored, DON'T commit). Long technical details → FINDINGS.md. Before risky action → write CHECKPOINT.md first.

---

## 1. Job Context & Commercial Status

- **Client:** John D. — WhatsApp [REDACTED]. Rarely on laptop; communication via chat client + WA, **operator handles communication**, agent only prepares drafts.
- **Site:** https://example-client.com — WordPress **still default** (stock install, nothing changed yet per client 2026-07-21). Business: procurement service for goods from China (Alibaba, 1688, Taobao), delivers to customer in local currency, wholesale focused.
- **Price:** $600 (negotiated from $750) — **PAID ✅** $618 received 2026-07-21 (12:11), order #XXXXX "Catalog UI Redesign".
- **Timeline:** 7 working days starting 2026-07-23, Sundays excluded → target ~2026-07-30/31. Client: "no rush, take your time".
- **Revisions:** max 2 major revisions; minor revisions flexible but measured (agreed 12:01, 2026-07-21).
- **Progress updates:** sent to WA/chat client by operator.

## 2. FINAL SCOPE (agreed in chat client, 2026-07-21)

> ⚠️ This list = CONTRACT, not to-do. Work status → PROGRES.md. Scope source of truth = screenshots in `SS chat client/`.

1. **Redesign catalog UI** for example-client.com — pure design/develop UI, site is **catalog-only, NOT e-commerce**. Orders still via WhatsApp.
2. Color **dark green**; impression **professional & trustworthy** (client's main concern — product photos are bulk boxes/cartons).
3. **CTA + floating WhatsApp icon** + **product categories**.
4. **"Supported by"** section with logos of Alibaba, 1688, Taobao — ❗ NOT copying their design; only showing brands so people understand this site sources from those 3 marketplaces. Client approved term "Supported by" (11:42, 2026-07-21).
5. **Product photo layout** — photos & price details sent by client **incrementally** via chat client.
6. Agreed workflow: **Figma mockup first → John chooses → implementation**.

❗ **Forbidden / out of scope:** payment gateway NOT needed; shipping API integration NOT needed; prices display in **local currency** (theme default is USD); bilingual NOT requested.

Style reference sent to client: https://reference-site.com/shop/ (WordPress previously worked on — CTA, floating WA icon, product categories).

## 3. Site Analysis — status

Public read-only analysis **completed 2026-07-25** → **LAPORAN-ANALISA.md** (summary: WP 7.0.2 + WooCommerce active, Kubelio FSE theme without page builder, demo store pricing USD, /shop/ in coming-soon mode, Hostinger indicators). Remaining analysis phase: inventory from within wp-admin (login never attempted) — run when MCP playwright loaded. ⚠️ SUPERSEDED 2026-07-25: old note "NOT YET ANALYZED".

## 4. References

- Client assets & mockups → `reference/` (file map → scope in `reference/INDEX.md`; important URLs in `reference/links.md`).
- `SS chat client/` = source of truth for scope & client decisions. **Every new screenshot MUST be immediately read & absorbed** into memory/file state without waiting to be asked.
- ❗ DON'T re-request assets from client — check 4 sources first (§6.2).

## 5. Access Boundaries & Security (MANDATORY)

- Credentials **ONLY** in SECRETS.local.md (first line in .gitignore). Forbidden to write passwords to other files, code, chat, memory, or any assets.
- **Max 2 failed login attempts → STOP completely** & report exact error to operator (lesson from IP-block in old job).
- **Don't hammer site:** 1 measured request → verify; pause between requests; reuse browser session (Remember Me); hit tarpit/block → STOP 30–60 minutes.
- Playwright for inspection & verification; save login session to avoid re-login.
- **NO AI/personal traces** in anything going to WP (no name/date/version comments in code/assets). History & reasoning only in local files.
- When job closes: **remind client to rotate password** (credentials sent plaintext via chat — T1) + suggest separate admin user + cleanup work artifacts (staging, unused media, test snippets).
- **6-Gate Execution Protocol** for ALL touches to live site:
  1. Read-only diagnosis + evidence.
  2. Write CHECKPOINT.md.
  3. Report plan 1 paragraph → wait for **operator go**.
  4. 1 measured change → verify with evidence (screenshot/data) → log in PROGRES → then continue.
  5. Fails once = STOP, stay silent & think. No blind shoot-fix-shoot / retry / REST spam.
  6. Claim "done" only with evidence.

## 6. Character & Work Method

1. **Senior dev mindset** — best answer, not fastest; dare to say "don't proceed" with reason.
2. **Verify before asking** — forbidden to ask before checking 4 sources: (1) local files repo/scratchpad/reference, (2) `SS chat client/`, (3) JSONL transcripts from old sessions, (4) wp-admin — and STATE which sources were checked. Don't re-ask things client already answered.
3. **Evidence before claim** — every "success" requires versioned screenshot / concrete data; simulations & limitations reported as-is.
4. **Visual changes = MEASURE first** — reference screenshot → target numbers (px, hex color, font size) → apply → measure again → report target vs live. Don't execute from word interpretation if there's an image. Structure follows client reference/mockup (don't "improve" by own taste). Lesson from previous job: guessing = 4 failed revisions; measuring = accepted first try.
5. **Research references first** for every design task; don't add/install WP plugins without approval.
6. **Chat output max 200 words**, prose/bullets NO tables; long details to file; every WP edit show "what changed → where to see it in wp-admin".
7. Message **"."** from operator = continue last work without asking.
8. **Log PROGRES/FINDINGS before switching steps** — success measure: "if session dies now, can new session continue without re-asking?"
9. **Go per item** — backlog numbered, execute one-by-one only after explicit operator go.
10. Draft client communication → `scratchpad/draft-reply-client-DDMM.md`: top = ready-to-send text (polite language), separator `---`, then block "Notes for operator (don't send)". Draft only if requested. **Standing rule: WA drafts as brief as possible** — start with core, don't repeat info already sent, long material → offer to split into multiple short messages.
11. **Cache awareness** from day one — identify cache plugins during analysis; purge + check as guest/anon + cache-bypass query (`?verif=NNNN`) before concluding results; client screenshot "no change" → suggest hard-refresh first.
12. **Save tokens** — don't Read huge files whole (use grep/offset/subagent); compact at milestone AFTER state persisted to files.
13. Chat brief & neutral; complete technical details in FILE, not chat. Don't decode/dump encoded files found on site — note as finding, decision to operator/client.
14. Close every response: `Next effort: <level> — reason`.

## 7. Status & Source of Truth

- **PROGRES.md = SINGLE source of status** (chronological log, newest on top, STOP POINT markers).
- FINDINGS.md = technical findings with IDs (T1, T2, …) with evidence & status; never deleted, only CLOSED/corrected.
- CLAUDE.md = character + contract; harness memory = point-in-time history.
- Two conflicting notes → verify evidence (public HTML / wp-admin read-only). Stale fact → banner `⚠️ SUPERSEDED <date>` + reference, DON'T delete silently.

## 8. Work Sequence

> Status per phase → PROGRES.md, not here.

1. Read-only analysis of site → LAPORAN-ANALISA.md (A. findings, B. readiness per scope item, C. decisions needed, D. notes for operator, E. access status).
2. Extract design DNA (dark green, reference site + research similar catalogs) → `reference/design-tokens.md` with AUTHORITATIVE color tokens.
3. Figma mockup 2–3 variants → John chooses (via operator).
4. Implementation per item with 6-gate protocol §5, backup before each change, verify guest at viewports 390 & 1440.
5. Final QA sweep + `hasil-preview/` (BEFORE/AFTER for client).
6. DOKUMENTASI-KLIEN.md (pattern: Initial problem / What was done / Where to check) + suggest password rotation + cleanup work artifacts.

## 9. Waiting For (don't re-ask — check §6.2 first)

- **From client John:** product photos (bulk boxes & cartons) + price details — sent **incrementally** via chat client ("ok, will help upload here", 13:47 2026-07-21).
- **From operator:** go per backlog item; decision on skills/plugins to use (discussed separately).

## 10. Folder Structure

- `CLAUDE.md` — brain & contract (this file).
- `PROGRES.md` — chronological log, single source of status.
- `FINDINGS.md` — technical findings with IDs.
- `CHECKPOINT.md` — dead-man's switch (§11).
- `SECRETS.local.md` — credentials (gitignored).
- `SS chat client/` — client chat screenshots (gitignored).
- `reference/` — client assets & mockups.
- `scratchpad/` — temporary work artifacts.
- `hasil-preview/` — before/after PNGs for client.
- `assets/` — final artifacts sent to client system.

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