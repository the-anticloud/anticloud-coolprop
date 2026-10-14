# Independent Insurance — COOLPROP

**Project:** COOLPROP  
**Category:** CHEMICAL_PRODUCTION  
**Upstream:** see BENCH.json  
**Pinned commit:** `d190a0f3d542756f02639a7ab4d22f54749287d4`  
**Assurance:** 16/16 checks passing  
**Ledger head:** `c47e489603f5f1c89a95cb5fc12a92bbd767842bfa554e722c6b0ba9a8065fdd`  
**Date:** October 2026

## Why AI-specific cover matters

Deploying AI in a regulated sector creates liability surfaces that ordinary
technology cover does not reach: inference liability, audit-trail liability,
data-breach liability and IP-infringement liability.

## How this project's architecture reduces insurable risk

| Risk | Cloud AI | COOLPROP with AIOSS |
|---|---|---|
| Audit-trail loss | high — vendor-controlled logs | low — append-only chain, verifiable offline |
| Data breach in transit | high — data transits external servers | low — no external endpoint |
| Compliance violation | high — cannot satisfy air-gap requirements | low — structural |
| IP liability | moderate | low — pinned provenance chain |

## Evidence package for an insurer

- AIOSS chain verification for head `c47e489603f5f1c89a95cb5fc12a92bbd767842bfa554e722c6b0ba9a8065fdd`
- The 16-check register with per-check evidence hashes
- Framework control mapping in `BENCH.json`

## Contact

lois@0-1.gg
