# CHECKPOINT — Dead-Man's Switch

> Write this BEFORE every risky action. If session dies badly, new session reads this file first.

---

## Last Entry

**Date/Time:** 2026-07-26 15:42
**Agent:** Agent 1

### (a) Action about to run
Change WooCommerce currency setting from USD to local currency via wp-admin → WooCommerce → Settings → General → Currency dropdown.

### (b) Current state
WooCommerce → Settings → General → Currency: "United States dollar ($)"
Shop page displays: "$0.00" for test product
No orders exist in system (verified wp-admin → WooCommerce → Orders)

### (c) How to verify if action already happened
Read-only check:
1. Browse to https://example-client.com/shop/ as guest (cache-bypass: ?verif=2607)
2. Check any product price format
3. Expected if action done: local currency symbol instead of "$"
4. OR: wp-admin → WooCommerce → Settings → General → Currency field value

### (d) Action per check result
- Action NOT yet happened → proceed with change per 6-gate protocol gate 4
- Action ALREADY happened & OK → log to PROGRES.md, move to next backlog item
- Action ALREADY happened & FAILED → check WooCommerce error log (wp-admin → WooCommerce → Status → Logs), restore from backup if currency corrupted, report exact error to operator before retry