# AnchorForge Site Log

**Public append-only log of runs submitted via [aiit-threshold.com/anchorforge](https://aiit-threshold.com/anchorforge).**

Every entry here is a **site-gated pre-check**, not a certified run.

- The read is done by **Claude Sonnet 4.6** (`claude-sonnet-4-6`) — chosen because Rhet considers it the most honest frontier model.
- Anchors are pinged (HTTP HEAD) to confirm they resolve. Dead links are flagged.
- The verdict is a fast, machine-adjudicated read — **not a human-verified certification**.

## UNCERTIFIED ≠ CERTIFIED

If you want the real thing — tamper-evident, OpenTimestamps-stamped, gated by two human verifiers — see **[AIIT-GLITCH/anchor-forge-protocol](https://github.com/AIIT-GLITCH/anchor-forge-protocol)**. Those runs live in `runs/RUN-XXX/` and the leaderboard in that repo's README is the authoritative one.

This repo exists so site-gated runs have a permanent, public, tamper-evident trail — but the site log is its own thing, never mixed with certified runs.

## Layout

```
runs/
  2026/
    04/
      17/
        {timestamp}-{model-slug}-{short-hash}.md
```

Each entry contains:

- Claimed model identifier (self-reported at top of run by the operator)
- Timestamp (UTC)
- SHA-256 of the raw output
- Raw output (verbatim)
- Site gate verdict (Sonnet 4.6's read)
- Anchor liveness map (HEAD ping results per URL)
- Gate Multiplier (x1.0 all live / x0.7 one dead / x0 two or more dead)

## Rate limits

- **Free (GitHub login):** 1 site-gate per calendar week
- **AnchorForge Pro ($4.99/mo):** 1 site-gate per calendar day

Gates are rate-limited per GitHub user. IP is secondary.

## Integrity

- Every commit to this repo is pushed from the site's GitHub write token.
- No one can edit a run after it lands. Forks welcome; tampering is visible in history.
- Closed loops: site -> this repo -> operator's own audit trail. No trust in Rhet or the site server required.

---

**Owned by Rhet Wike - AIIT-THRESHOLD LLC - Council Hill, Oklahoma**
