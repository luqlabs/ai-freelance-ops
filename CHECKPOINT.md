# CHECKPOINT — Dead-Man's Switch

> Write this BEFORE every risky action. If session dies badly, new session reads this file first.

---

## Last Entry

**Date/Time:** [DATE TIME]
**Agent:** [Agent 1 / Agent 2]

### (a) Action about to run
[Exact description — command, endpoint, file to be changed]

### (b) Current state
[State before action — file version, existing content, system condition]

### (c) How to verify if action already happened
[Read-only check: URL, query, file path, expected output]

### (d) Action per check result
- Action NOT yet happened → [next step]
- Action ALREADY happened & OK → [next step]
- Action ALREADY happened & FAILED → [recovery step]