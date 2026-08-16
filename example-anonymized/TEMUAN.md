# TEMUAN — Catalog UI Redesign

> Technical facts with IDs. Never deleted — only CLOSED or SUPERSEDED with forward reference.

---

**T1 — Credentials sent plaintext via chat** | Status: OPEN
- **Evidence:** chat log 2026-07-21, 14:32
- **Implication:** leak risk if chat platform compromised
- **Action:** remind client to rotate password at job close; suggest separate admin user for future work

**T2 — WooCommerce currency set to USD, needs local currency** | Status: OPEN
- **Evidence:** wp-admin → WooCommerce → Settings → General → Currency: "United States dollar ($)"
- **Implication:** scope §2 requires local currency display; client business operates in local currency
- **Action:** change currency setting during implementation phase (gate 3 protocol)

**T3 — Store still in demo mode with coming-soon notice** | Status: OPEN
- **Evidence:** WooCommerce → Settings → Store Notice: "This is a demo store. No orders will be fulfilled."
- **Implication:** not blocking development; client aware site still default install
- **Action:** disable store notice + coming-soon mode after product import complete

**T4 — W3 Total Cache plugin active** | Status: OPEN
- **Evidence:** wp-admin → Plugins → W3 Total Cache 2.7.0 active
- **Implication:** cache must be purged after every change; verify as guest/anon required per §6.11
- **Action:** add cache purge step to 6-gate protocol; document purge method in CHECKPOINT.md

**T5 — Kubelio FSE theme v1.2.1 (no page builder)** | Status: OPEN
- **Evidence:** wp-admin → Appearance → Themes → Kubelio FSE v1.2.1 active
- **Implication:** Full Site Editing workflow (block editor); no Elementor/Divi; customization via theme.json + block patterns
- **Action:** research Kubelio FSE block patterns for floating WA button + category grid implementation

**T6 — Zero products in catalog, waiting for client photos** | Status: OPEN
- **Evidence:** wp-admin → Products → "No products found"
- **Implication:** mockup phase needs placeholder images; real product import after mockup approved
- **Action:** use stock bulk box/carton photos for mockup; document import workflow for client incremental photo uploads